---
title : RectangularLayout
parent: API
grand_parent : Documentation
---
## Summary
RectangularLayout methods:
RectangularLayout - is a class.
compute_losses_stranded - RectangularLayout/compute_losses_stranded is a function.
create_solid_geometry - RectangularLayout/create_solid_geometry is a function.
## PROPERTIES
* RectangularLayout/conductor_height is a property.

* RectangularLayout/conductor_width is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * RectangularLayout/RectangularLayout is a constructor.

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
Help for RectangularLayout/compute_losses_stranded is inherited from superclass WINDINGLAYOUTBASE

### * conductor_area Total conductor area per slot.

Returns nan by default; should be overridden in subclasses if
needed.
Help for RectangularLayout/conductor_area is inherited from superclass WINDINGLAYOUTBASE

### * create_solid_geometry Create slot geometry for solid winding
models.
Help for RectangularLayout/create_solid_geometry is inherited from superclass WINDINGLAYOUTBASE

