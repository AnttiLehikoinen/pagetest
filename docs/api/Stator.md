---
title : Stator
parent: API
grand_parent : Documentation
---
## Summary
Stator General-purpose stator class for symmetric slotted stators.

Supports:

* inrunner and outrunner geometries

* 1- and 2-layer windings

* Distributed- and concentric-style layer orientations (radial and
circumferential)

Run Stator.list_dimensions to show available dimensions.
## PROPERTIES
* slot - SlotShapeBase object

## Methods
Class methods are listed below. Inherited methods are not included.
### * Stator General-purpose stator class for symmetric slotted stators.

Supports:

* inrunner and outrunner geometries

* 1- and 2-layer windings

* Distributed- and concentric-style layer orientations (radial and
circumferential)

Run Stator.list_dimensions to show available dimensions.

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.
Help for Stator/create_geometry is inherited from superclass GEOBASE

### * list_dimensions Display dimensions info on command window
Help for Stator.list_dimensions is inherited from superclass GEOBASE

### * save_to_excel Save specifications to Excel sheet.

save_to_excel(this, fname, varargin)
Help for Stator/save_to_excel is inherited from superclass GEOBASE

