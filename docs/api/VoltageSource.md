---
title : VoltageSource
parent: API
grand_parent : Documentation
---
## Summary
VoltageSource Voltage source class for MagneticsProblem.

Initialization:

S = VoltageSource(motor) for sinusoidal voltage supply.

S = VoltageSource(motor, modulator) to use a custom modulator,
e.g. SVPWM_Modulator.
## PROPERTIES
* VoltageSource/Mout is a property.

* VoltageSource/Uab is a property.

* VoltageSource/Udq is a property.

* VoltageSource/average is a property.

* modulator - FIXME generalize call syntax

* VoltageSource/motor is a property.

* VoltageSource/phases is a property.

* VoltageSource/tprev is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * U instantaneous voltage.

Uout = U(this, circuit, problem, type, t, k, inds, X), where

* circuit : parent Circuit object

* problem : a MagneticsProblem

* type : harmonic / stepping

* t : time

* k : index of time-step

* inds : indices to voltage-current variables corresponding
to the parent Circuit

* X : raw solution vector of the *previous*  time-step.

### * VoltageSource Voltage source class for MagneticsProblem.

Initialization:

S = VoltageSource(motor) for sinusoidal voltage supply.

S = VoltageSource(motor, modulator) to use a custom modulator,
e.g. SVPWM_Modulator.

### * VoltageSource/recover_voltages is a function.
U = recover_voltages(this, solution)

### * set_Udq Set d- and q-components of phase supply voltages.

