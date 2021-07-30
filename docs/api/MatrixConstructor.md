---
title : MatrixConstructor
parent: API
grand_parent : Documentation
---
## Summary
MatrixConstructor Constructor for FE matrices.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * MatrixConstructor Constructor

this = MatrixConstructor()

Initialize empty constructor.

this = MatrixConstruct(varargin)

Initialize AND then call this.assemble_matrix(varargin)

### * assemble_matrix Increment matrix.

assemble_matrix(this, fun_test, fun_shape, v, elements, msh)

Input arguments:

fun_test : test function. Typically Nodal2D or variants.

### * MatrixConstructor/assemble_vector is a function.
this = assemble_vector(this, fun_test, k, v, elements, msh, varargin)

### * no elements listed --> going over all

