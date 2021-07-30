---
title : BoundaryMatrixConstructor
parent: API
grand_parent : Documentation
---
## Summary
BoundaryMatrixConstructor is a class.
this = BoundaryMatrixConstructor(varargin)
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * BoundaryMatrixConstructor/BoundaryMatrixConstructor is a constructor.
this = BoundaryMatrixConstructor(varargin)

### * BoundaryMatrixConstructor/assemble_flux_matrix is a function.
this = assemble_flux_matrix(this, varargin)

### * assemble_matrix boundary matrix.

assemble_matrix(fun_test, fun_shape, v, edges, msh) :
Int[ fun_test \dot (v*fun_shape) ]
evaluated over edges

