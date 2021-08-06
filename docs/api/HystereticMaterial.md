---
title : HystereticMaterial
parent: API
grand_parent : Documentation
---
## Summary
HystereticMaterial Material class for hysteretic materials.

A valid HysteresisModel has to be set to this.hysteresis_model.

WARNING: HystereticMaterial objects are stateful, associated with the
latest [MagneticsSolution](MagneticsSolution.html). Thus, calling

`solution_1 = problem.solve_xx`
`solution_2 = problem_solve_xx`
`losses = MaterialBase.losses(solution_1)`

will result in **incorrect**  results or a crash.
## PROPERTIES
* Bcand - candidate B values, current Newton iteration

* Bvalues - computed values of B, 2xNexNsteps array

* Hcand - same for H

* Hvalues - the same for H

* Nsteps - number of time-steps to be expected

* dynamic_hysteresis_coefficient - computed automatically

* electrical_conductivity - electrical conductivity of the material (S)

* HystereticMaterial/hysteresis_model is a property.

* ndim - FIXME parse at init

* sheet_thickness - lamination sheet thickness (m)

* step - current time-step

* tnow - current time

* tprev - previous time

## Methods
Class methods are listed below. Inherited methods are not included.
### * HystereticMaterial Material class for hysteretic materials.

A valid HysteresisModel has to be set to this.hysteresis_model.

WARNING: **HystereticMaterial** objects are stateful, associated with the
latest [MagneticsSolution](MagneticsSolution.html). Thus, calling

`solution_1 = problem.solve_xx`
`solution_2 = problem_solve_xx`
`losses = MaterialBase.losses(solution_1)`

will result in **incorrect**  results or a crash.

### * basic copy stuff

### * compute_anhysteretic_curves Compute anhysteretic BH curves from the
hysteresis model.

Sets the material anhysteretic BH curves (this.B, this.H) to those
computed from the hysteresis model. The computation is done by simulating
symmetric BH loops of successively larger amplitude, and collecting the
(max(B), max(H)) point.

NOTE: in general, the aforementioned point may not be the true "corner"
point of the BH loop.

### * differential_reluctivity Return reluctivity and its derivative.

[nu, dnu] = differential_reluctivity(this, Bvector, true)

Return reluctivity and its derivative w.r.t. `B` ^2 computed with the
harmonic approximation

[H, dHdB] = differential_reluctivity(this, Bvector)

Return magnetic field strength vector and the differential reluctivity
tensor. Only works in 2D.
Help for HystereticMaterial/differential_reluctivity is inherited from superclass MATERIAL

### * evaluate_dynamic_H Evaluate dynamic hysteresis effect.

Dynamic hysteresis is modelled as

H_dynamic = this.electrical_conductivity ** this.sheet_thickness^12 **
1/12 * dB/dt

Call syntax:

[H, dHdB] = evaluate_dynamic_H(this, kstep, B), where

* kstep : index of current time-step

* B : flux density vector at current time-time

Return values:

* H : field strength associated with the dynamic hysteresis

* dHdB : differential reluctivity

H = evaluate_dynamic_H(this, timestamps) computes the value of H at all
time-steps, from this.Bvalues.

### * init_for_problem Initialize object for problem.

Normally, this method does very little apart from determining the
stacking factors. It could be used to initialize hysteresis models or
similar in subclasses on Material, though.
Help for HystereticMaterial/init_for_problem is inherited from superclass MATERIAL

### * loss_density Elementwise loss density.

Hysteresis loss density is computed as Hirr * dB/dt, where Hirr is the
'irreversible' field component, approximated here as

Hirr = H - Han(B) - Heddy, where

* Han(B) : anhysteretic field strength, computed with the anhysteretic
BH curve (this.B, this.H) and the current value of B

* Heddy : dynamic hysteresis field strength, computed with
`this.evaluate_dynamic_H` .

See MaterialBase.loss_density for input/output syntax.

### * set_step Set new time-step.

set_step(this, kstep, t, varargin)

