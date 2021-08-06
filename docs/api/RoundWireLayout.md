---
title : RoundWireLayout
parent: API
grand_parent : Documentation
---
## Summary
RoundWireLayout Winding layout class for random-wound coils.

The class tries to utilize existing magnet wire data, IEC standard,
loaded from the Excel sheet WireSizes.xlsx, in turn parsed from
Elektrisola and Hitachi datasheets (enamelled_copper_wire_english.pdf
and MagnetWire_en.pdf, respectively).
## PROPERTIES
* breakdown_voltage - minimum breakdown voltage

* diameter - nominal **diameter** (m)

* grade - insulation grade, IEC (= 1, 2, 3) %FIXME setter method

* maximum_outer_diameter - maximum outer diameter

* RoundWireLayout.wire_data is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * RoundWireLayout Winding layout class for random-wound coils.

The class tries to utilize existing magnet wire data, IEC standard,
loaded from the Excel sheet WireSizes.xlsx, in turn parsed from
Elektrisola and Hitachi datasheets (enamelled_copper_wire_english.pdf
and MagnetWire_en.pdf, respectively).

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
Help for RoundWireLayout/compute_losses_stranded is inherited from superclass WINDINGLAYOUTBASE

### * conductor_area Total conductor area per slot.

Returns nan by default; should be overridden in subclasses if
needed.
Help for RoundWireLayout/conductor_area is inherited from superclass WINDINGLAYOUTBASE

### * RoundWireLayout/create_solid_geometry is an undocumented builtin RoundWireLayout method.

### * gross_conductor_area Conductor area WITH insulation.

Returns the gross conductor area: useful area plus
insulation, per single conductor. Returns nan by default,
should be subclassed.
Help for RoundWireLayout/gross_conductor_area is inherited from superclass WINDINGLAYOUTBASE

