---
title : HollowConductorLayout
parent: API
grand_parent : Documentation
---
## Summary
HollowConductorLayout methods:
HollowConductorLayout - is a class.
compute_losses_stranded - HollowConductorLayout/compute_losses_stranded is a function.
create_solid_geometry - HollowConductorLayout/create_solid_geometry is a function.
## PROPERTIES
* HollowConductorLayout/conductor_height is a property.

* HollowConductorLayout/conductor_width is a property.

* HollowConductorLayout/inner_diameter is a property.

* HollowConductorLayout/number_of_columns is a property.

* HollowConductorLayout/outer_diameter is a property.

* HollowConductorLayout/packing is a property.

* HollowConductorLayout/shape is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * HollowConductorLayout/HollowConductorLayout is a constructor.

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
Help for HollowConductorLayout/compute_losses_stranded is inherited from superclass WINDINGLAYOUTBASE

### * conductor_area Total conductor area per slot.

Returns nan by default; should be overridden in subclasses if
needed.
Help for HollowConductorLayout/conductor_area is inherited from superclass WINDINGLAYOUTBASE

### * create_solid_geometry Create slot geometry for solid winding
models.
Help for HollowConductorLayout/create_solid_geometry is inherited from superclass WINDINGLAYOUTBASE

