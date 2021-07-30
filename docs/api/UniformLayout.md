---
title : UniformLayout
parent: API
grand_parent : Documentation
---
## Summary
UniformLayout Layout specification for non-specified layouts:

* Stranded windings are modelled as infinitely stranded, with zero AC
losses and filling the entire slot surface area. NOTE: filling factor
IS taken into account inside [PolyphaseCircuit](PolyphaseCircuit.html).

* Solid winding fill the entire slot area.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * UniformLayout Layout specification for non-specified layouts:

* Stranded windings are modelled as infinitely stranded, with zero AC
losses and filling the entire slot surface area. NOTE: filling factor
IS taken into account inside [PolyphaseCircuit](PolyphaseCircuit.html).

* Solid winding fill the entire slot area.

### * compute_losses_stranded Estimate AC losses in stranded windings.

Estimate AC loss distribution for stranded (= non-solid)
conductor models.

[p_el, data] = compute_losses_stranded(this, winding_spec, dBx,
dBy, conductivity), where

* winding_spec : [PolyphaseWindingSpec](PolyphaseWindingSpec.html) object for specifying the
winding.

* dBx, dBy : time-derivative of flux density

* conductivity : electrical conductivity, assumed uniform.

See the code of PolyphaseCircuit.stranded_conductor_losses for
more details.
Help for UniformLayout/compute_losses_stranded is inherited from superclass WINDINGLAYOUTBASE

### * create_solid_geometry Create slot geometry for solid winding
models.
Help for UniformLayout/create_solid_geometry is inherited from superclass WINDINGLAYOUTBASE

### * UniformLayout/number_of_meshed_conductors_per_layer is a function.
n = number_of_meshed_conductors_per_layer(this, ~)

