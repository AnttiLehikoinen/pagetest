---
title : NodalBase
parent: API
grand_parent : Documentation
---
## Summary
NodalBase is a class.
this = NodalBase(oper)
## PROPERTIES
* NodalBase/Nf is a property.

* NodalBase/op is a property.

* NodalBase/order is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * NodalBase/NodalBase is a constructor.
this = NodalBase(oper)

### * EVAL Execute MATLAB expression in text.
EVAL(EXPRESSION) evaluates the MATLAB code in EXPRESSION. Specify
EXPRESSION as a character vector or string scalar.

[OUTPUT1,...,OUTPUTN] = EVAL(EXPRESSION) returns output from EXPRESSION
in the specified variables.

Example: Interactively request the name of a matrix to plot.

expression = input('Enter the name of a matrix: ','s');
if (exist(expression,'var'))
plot(eval(expression))
end

See also FEVAL, EVALIN, ASSIGNIN, EVALC.

### * NodalBase/getData is a function.
[Nf, order, Nvars] = getData(this, msh)

### * NodalBase/getIndices is a function.
inds = getIndices(~, k, msh, varargin)

### * NodalBase/instantiate_subclass_for_mesh is a function.
Nmsh = instantiate_subclass_for_mesh(N, msh)

