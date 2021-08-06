---
title : Nodal3D
parent: API
grand_parent : Documentation
---
## Summary
Nodal3D is a class.
this = Nodal3D(varargin)
## PROPERTIES
* Nodal3D/op is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nodal3D/Nodal3D is a constructor.
this = Nodal3D(varargin)

### * eval evaluates the global shape function
call syntax
eval(k, X, msh, F, detF) or
eval(k, X, msh, elements)

### * evaluates the reference shape function (either identity or
gradient)

### * Nodal3D/eval_tet is a function.
Nref = eval_tet(this, k, X, msh)

### * getData

### * Nodal3D/getIndices is a function.
inds = getIndices(~, k, msh, varargin)

