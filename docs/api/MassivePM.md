---
title : MassivePM
parent: API
grand_parent : Documentation
---
## Summary
MassivePM methods:
MassivePM - is a class.
create_geometry - MassivePM/create_geometry is a function.
save_to_excel - MassivePM/save_to_excel is a function.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * MassivePM/MassivePM is a constructor.
this = MassivePM(dim)

### * copy_domain Copy domain and apply necessary rotations or
translations.

new = copy_domain(this, old_domain, sector_shift)

DEFAULT behaviour: rotate domain remanence and orientation
directions, if any, by sector_shift.

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.
Help for MassivePM/create_geometry is inherited from superclass GEOBASE

### * save_to_excel Save specifications to Excel sheet.

save_to_excel(this, fname, varargin)
Help for MassivePM/save_to_excel is inherited from superclass GEOBASE

