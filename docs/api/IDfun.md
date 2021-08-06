---
title : IDfun
parent: API
grand_parent : Documentation
---
## Summary
IDfun is a class.
this = IDfun(varargin)
## PROPERTIES
* IDfun/k is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * IDfun/IDfun is a constructor.
this = IDfun(varargin)

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

### * IDfun/getData is a function.
[Nf, order, Nvars] = getData(~, ~)

### * IDfun/getIndices is a function.
inds = getIndices(this, ~, ~, ~)

