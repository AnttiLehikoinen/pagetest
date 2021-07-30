---
title : WindingLayoutBase
parent: API
grand_parent : Documentation
---
## Summary
WindingLayoutBase Base class for winding layouts.

A winding layout (sub)class is responsible for three things:

* containing the required parameters, if any, for specifying the
layout (e.g. diameter of a wire)

* Creating the winding geometry inside a slot [Surface](Surface.html) for a given
[GeoBase](GeoBase.html) object.

* Estimating AC losses of stranded winding models.
## PROPERTIES
* interlayer_insulation_length - linear interlayer insulation length

* interlayer_insulation_thickness Interlayer insulation thickness.

If not specified, slot liner thickness x 2 is returned.

* slot_liner_length - linear slot liner length

* slot_liner_thickness - slot liner thickness (m)

* winding_window_area - winding window area, gross

## Methods
Class methods are listed below. Inherited methods are not included.
### * WindingLayoutBase Base class for winding layouts.

A winding layout (sub)class is responsible for three things:

* containing the required parameters, if any, for specifying the
layout (e.g. diameter of a wire)

* Creating the winding geometry inside a slot [Surface](Surface.html) for a given
[GeoBase](GeoBase.html) object.

* Estimating AC losses of stranded winding models.

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

### * conductor_area Total conductor area per slot.

Returns nan by default; should be overridden in subclasses if
needed.

### * create_slot_geometry Create the winding geometry.

This method creates the winding geometry, creating the necessary
[Material](Material.html) and [Domain](Domain.html) objects.

create_slot_geometry(this, parent_geometry, winding_spec,
slot), where

* parent_geometry : a [GeoBase](GeoBase.html) object

* winding_spec : a [PolyphaseWindingSpec](PolyphaseWindingSpec.html) object.

* slot : SlotShape object.

Depending on the winding model, this method typically calls
either the create_stranded_geometry or create_solid_geometry
methods.

### * create_solid_geometry Create slot geometry for solid winding
models.

### * create_stranded_geometry Finalize slot geometry of stranded windings.

### * gross_conductor_area Conductor area WITH insulation.

### * parse_slot_data Parse slot area, liner/insulation lengths.

### * uninsulated_winding_area Winding window area minus liners.

