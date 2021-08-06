---
title : PCBStator
parent: API
grand_parent : Documentation
---
## Summary
PCBStator methods:
PCBStator - is a class.
create_geometry - PCBStator/create_geometry is a function.
## PROPERTIES
* PCBStator/winding_spec is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nrep Number of times to replicate elementary mesh.

Nrep(this)

Usually subclassed, but by default returns
this.dimensions.Nrep.
Help for PCBStator/Nrep is inherited from superclass GEOBASE

### * PCBStator/PCBStator is a constructor.
this = PCBStator(dim)

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.
Help for PCBStator/create_geometry is inherited from superclass GEOBASE

### * PCBStator/sector_shift is a function.
sa = sector_shift(this)

### * winding_angle Return winding angle.

