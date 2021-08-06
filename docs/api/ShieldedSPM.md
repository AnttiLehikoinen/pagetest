---
title : ShieldedSPM
parent: API
grand_parent : Documentation
---
## Summary
ShieldedSPM methods:
ShieldedSPM - is a class.
create_geometry - ShieldedSPM/create_geometry is a function.
save_to_excel - ShieldedSPM/save_to_excel is a function.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * ShieldedSPM/ShieldedSPM is a constructor.
this = ShieldedSPM(dim)

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.
Help for ShieldedSPM/create_geometry is inherited from superclass GEOBASE

### * ShieldedSPM.parse_IRdim is a function.
dim = parse_IRdim(irdim)

### * ShieldedSPM/parse_thor is a function.
datr = parse_thor(this)

### * save_to_excel Save specifications to Excel sheet.

save_to_excel(this, fname, varargin)
Help for ShieldedSPM/save_to_excel is inherited from superclass GEOBASE

