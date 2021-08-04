---
title : MaterialBase
parent: API
grand_parent : Documentation
---
## Summary
MaterialBase Base class for materials.

Not really used right now, see [Material](Material.html).
## PROPERTIES
* B - given B-curve (T)

* H - given H-curve (A/m)

* domains - list of **domains** that are made of this material

* elements - indices to finite elements

* iron_loss_computation_method Iron loss computation method.

This property allows an option to toggle the iron loss
computation method. Indeed, the `loss_density`  method of the
[Material](Material.html) class calls the method with its name equal to this
property.

However, subclasses may have a different `loss_density`  method.

* is_symmetric - Is the differential reluctivity symmetric?

* material_properties Struct of material properties

Important fields include:

* rho : material density, kg/m^3

* coeffs : [hysteresis, eddy, excess] loss coefficients,
defined as W/kg at 50 Hz and 1 T, with B-f dependencies as
~[fB^2, (fB)^2, (fB)^.1] respectively. Used mainly in the
[Material](Material.html) class.

* plot_args - plotting instructions for this

## Methods
Class methods are listed below. Inherited methods are not included.
### * MaterialBase Base class for materials.

Not really used right now, see [Material](Material.html).

### * MaterialBase/detach is a function.

### * MaterialBase/differential_reluctivity is a function.

### * get_B_data Compute flux density waveforms and other data.

Bdata = get_B_data(solution, args)

Bdata is an array of structs with the fields (one struct per quadrature
point)

* solution : handle to the [MagneticsSolution](MagneticsSolution.html) used

* timestamps : time-step timestamps in seconds

** volume_multiplier : model.dimensions.leff **  model.symmetrySectors

* DETF : absolute value of mesh mapping matrix determinant at quad point

* Bx : waveform of x-component of flux density at quad point

* By : waveform of y-component of flux density at quad point

### * MaterialBase/init_for_problem is a function.

### * loss_density Iron/material loss density method.

[p_hysteresis, p_eddy, p_excess] = loss_density(this, Bdata), where

* Bdata : flux density waveform data returned by `get_B_data` .

Return values:

* Elementwise hysteresis, eddy, and exces loss densities,
expressed in W/m^3.

### * losses Material-level loss computation.

[Ptot, Pdata] = losses(solution) or

[Ptot, Pdata] = losses(solution, key, value, ...) (see below)

return the total material (usually iron)
losses Ptot for [MagneticsSolution](MagneticsSolution.html) solution.

Pdata is then a struct with the following fields:

Return values: total **losses** (time-average) and a loss data struct with
the following fields:

* P_total : average total losses

* P_total_time : total **losses** versus time (solution.ts)

* P_hysteresis : total hysteresis losses

* P_eddy : total eddy-current iron losses

* P_excess : total excess losses.

* P_rotor : total **losses** in rotor (in elements motor.rotel)

* P_hysteresis_rotor : total hysteresis **losses** in rotor

* P_eddy_rotor

* p_hysteresis_elementwise : vector of elementwise hysteresis loss
density (W/m^3)

* p_eddy_elementwise

* p_excess_elementwise

WARNING: element-wise loss densities are returned in W/m^3, as opposed to
the W/kg used in previous versions.

The **losses** are computed by first computing the flux density waveforms
with MaterialBase.get_B_data, and then passing the results to
the `.loss_density`  method of each  [Material](Material.html) in the solution, to get the
elementwise loss densities. The **losses** are then summed and  the
other interesting outputs computed.

Keyword arguments:

* plotting_on : plot results (default false). Losses are plotted with
MaterialBase.plot_losses

* remove_DC : Remove DC-component of flux density before computing
losses? Options: false - no removal / 'rotor' - only remove from rotor
elements (motor.rotel) / 'all' remove from all elements.

* use_entire_solution : use entire solution range (in time-domain).
Default: false: only last full electrical period is used.

* method : This value is temporarily set as the
`iron_loss_computation_method`  property of each [Material](Material.html). For the plain
[Material](Material.html) class, the options are
"iron_loss_density_time_domain_Steinmetz" and
"iron_loss_density_frequency_domain_Bertotti". Subclasses may ignore
this. Default : [] --> don't change the property value.

### * MaterialBase/plot_BH is a function.

### * MaterialBase/raw_reluctivity is a function.

