---
layout: default
title: Iron loss modelling
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Iron loss modelling in finite-element analysis

Modelling iron losses is generally regarded as difficult. So far, no generally-accepted best solution has emerged.

The different modelling approaches can be divided into two categories:

1. Post-processing models

1. Online models

The following subsections briefly introduce these two, and summarize their implementation in `EMDtool`.

# Post-processing models

In post-processing approaches, the actual finite-element solution is computed *without* considering the iron losses. Indeed, the nonlinear behaviour of ferromagnetic materials is
represented by their anhysteretic (single-valued) BH-curve only, independent of their rate of change or past behaviour.

The iron losses are then estimated after the solution, from the computed flux density waveforms. Currently, there are two approaches in `EMDtool`.

## Frequency-domain Bertotti model

In the frequency-domain Bertotti model, the computed flux density waveforms are then decomposed into their different frequency components, using the fast fourier transform (`fft`).

The total iron loss power density (in W/m^3 or W/kg) is then computed with the following formula:

$$ p = \sum\limits_{n=1}^N c_\text{hysteresis} f_n B_n^2 + c_\text{eddy} (f_n B_n)^2 \quad \left( + c_\text{excess} (f_n B_n)^{1.5} \right) .$$

Of this, the actual losses are then computed by integrating the loss density over the problem volume.

Note that depending on the author/context, the excess loss term may or may not be included. Indeed, even most `EMDtool` materials are modelled without it, as better fits with measured losses are often obtained
this way.

**NOTE:** This model pretty much requires that a full electrical period is simulated. Otherwise, the model typically 'sees' a very large jump in flux density. This is because FFT essentially
thinks that the signal given to it is periodic - that after reaching its end, it continues again from the beginning.

**NOTE:** Machines with concentrated windings often have significant subharmonics, meaning that several electrical periods have to be analysed, to simulate an entire electrical period in the rotor frame.

## Time-domain Steinmetz model

The Steinmetz model propably means different things to different authors. Without further discussion, the approach adopted in `EMDtool` is the following:

$$ p(t) = c_\text{hysteresis} \left| B(t) \right|^a  \left| \frac{\text{d}B(t)}{\text{d}t} \right|^b +  c_\text{eddy} \left( \frac{\text{d}B(t)}{\text{d}t} \right)^2 $$

By default, the hysteresis loss exponents $$a, b$$ are both equal to 1.

## `EMDtool` details and notes

By default (see the [Material](../../api/Material.html) class), the Bertotti model loss coefficients are stored in the `.coeffs` field of the `.material_properties` property-struct of the Material object.
These coefficient denote the loss density *per kilogram, at 50 Hz frequency and sinusoidal flux density at 1 T peak value*.

The `.iron_loss_density_frequency_domain_Bertotti` method is then used to compute the loss density in (W/m^3), using the Bertotti approach.

The `.iron_loss_density_time_domain_Steinmetz` then returns the losses from the Steinmetz approach. The same loss coefficients are used as for the Bertotti model, plus suitable scaling.

The intended way of computing the losses is the [`MaterialBase.losses`](../../api/MaterialBase.html#-losses-material-level-loss-computation), which then calls the `.loss_density` method of each
Material in the `problem`. For the basic [Material](../../api/Material.html) class, the behaviour of the `losses` method can be toggled by using the `iron_loss_computation_method` property.

### 2-dimensional flux densities

Perhaps the most significant difference between the textbook Bertotti/Steinmetz model is that they are typically given in 1D form, while finite element analysis results are very much 2D (or 3D). 

Long story short and all discussion aside, the approach taken by `EMDtool` (at the time of writing at least) is to sum the contributions from the different axes together.

That means, using

$$ B_n := \sqrt{ B_{x,n}^2 + B_{y,n}^2 } $$

in the Bertotti model, and

$$ \left( \frac{\text{d}B(t)}{\text{d}t} \right)^2 := \left( \frac{\text{d}B_x(t)}{\text{d}t} \right)^2 + \left( \frac{\text{d}B_y(t)}{\text{d}t} \right)^2 $$

$$ \left| B(t) \right|^a  \left| \frac{\text{d}B(t)}{\text{d}t} \right|^b := \left| B_x(t) \right|^a  \left| \frac{\text{d}B_x(t)}{\text{d}t} \right|^b + \left| B_y(t) \right|^a  \left| \frac{\text{d}B_y(t)}{\text{d}t} \right|^b $$

for the Steinmetz model.

However, **suggestions for improvements are more than welcome**.

### DC-flux bias

Losses under DC-biased flux density (hello rotors) are another tricky issue.

The Bertotti model ignores the DC-bias altogether, which is know to underestimate the losses to some degree.

By contrast, the Steinmetz model tends to overestimate the hysteresis losses, due to the B-term in the equation. The `remove_DC` argument can be given to the [`MaterialBase.losses`](../../api/MaterialBase.html#-losses-material-level-loss-computation)
method, to remove the DC-flux component from either the rotor, stator, or all domains of the model, to (over)compensate for this issue.

# Online methods

In online computation methods, the hysteretic behaviour of magnetic materials is directly taken into account while running the simulation. More specifically, the BH-behaviour of the material now
depends on its past behaviour. 