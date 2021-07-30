---
title : MaterialSet
parent: API
grand_parent : Documentation
---
## Summary
MaterialSet Container class.

This class is used inside [MagneticsProblem](MagneticsProblem.html) analysis functions
for evaluating the reluctivities of a bunch of materials.
## PROPERTIES
* MaterialSet/harmonic_coupling_factor is a property.

* materials - **materials** included

## Methods
Class methods are listed below. Inherited methods are not included.
### * MaterialSet Container class.

This class is used inside [MagneticsProblem](MagneticsProblem.html) analysis functions
for evaluating the reluctivities of a bunch of materials.

### * evaluate_differential_reluctivity Differential reluctivity
evaluation.

[H, dHdB] = evaluate_differential_reluctivity(this, B)

[H, dHdB] = evaluate_differential_reluctivity(this, false)

[nu, dnudB] = evaluate_differential_reluctivity(this, true)

### * evaluate_raw_reluctivity Evaluate (non-differential) reluctivity.

### * is_symmetric Are all materials "symmetric".

Returns true if all this.materials are symmetric (return
symmetric differential reluctivity tensors).

### * set_step Set step.

