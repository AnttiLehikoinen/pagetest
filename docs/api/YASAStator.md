---
title : YASAStator
parent: API
grand_parent : Documentation
---
## Summary
YASAStator Axial yokeless stator.

Can be modelled as half or full.
## PROPERTIES
* YASAStator/winding is a property.

* YASAStator/winding_spec is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nrep Number of times to replicate elementary mesh.

Nrep(this)

Usually subclassed, but by default returns
this.dimensions.Nrep.
Help for YASAStator/Nrep is inherited from superclass GEOBASE

### * YASAStator Axial yokeless stator.

Can be modelled as half or full.

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.
Help for YASAStator/create_geometry is inherited from superclass GEOBASE

### * YASAStator/sector_shift is a function.
s = sector_shift(this)

### * winding_angle Return winding angle.

