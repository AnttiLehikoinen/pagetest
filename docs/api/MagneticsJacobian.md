---
title : MagneticsJacobian
parent: API
grand_parent : Documentation
---
## Summary
MagneticsJacobian methods:
MagneticsJacobian - is a class.
eval - Evaluate Jacobian.
eval_complex - MagneticsJacobian/eval_complex is a function.
init_assembly - Initialize MagneticsJacobian.
## PROPERTIES
* MagneticsJacobian/DETF is a property.

* MagneticsJacobian/Fvals_shape is a property.

* MagneticsJacobian/Fvals_test is a property.

* MagneticsJacobian/Ires is a property.

* ~= (NE)   Not equal relation for handles.
Handles are equal if they are handles for the same object and are
unequal otherwise.

H1 ~= H2 performs element-wise comparisons between handle arrays H1
and H2.  H1 and H2 must be of the same dimensions unless one is a
scalar.  The result is a logical array of the same dimensions, where
each element is an element-wise equality result.

If one of H1 or H2 is scalar, scalar expansion is performed and the
result will match the dimensions of the array that is not scalar.

TF = NE(H1, H2) stores the result in a logical array of the same
dimensions.

See also MAGNETICSJACOBIAN, MAGNETICSJACOBIAN/EQ, MAGNETICSJACOBIAN/GE, MAGNETICSJACOBIAN/GT, MAGNETICSJACOBIAN/LE, MAGNETICSJACOBIAN/LT
Help for MagneticsJacobian/Ne is inherited from superclass HANDLE

* MagneticsJacobian/dof_shape is a property.

* MagneticsJacobian/materials is a property.

* MagneticsJacobian/msh is a property.

* MagneticsJacobian/symmetric is a property.

* MagneticsJacobian/w is a property.

* MagneticsJacobian/x_quad is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * MagneticsJacobian/MagneticsJacobian is a constructor.
this = MagneticsJacobian(problem, symmetric, test_fun, shape_fun)

### * eval Evaluate Jacobian.

[J, res] = eval(this, X), where

X = discretized vector potential solution

Returns:

J = Jacobian matrix

res = residual vector

### * MagneticsJacobian/eval_complex is a function.
[Jrr, Jri, Jir, Jii, resr, resi] = eval_complex(this, X)

### * init_assembly Initialize MagneticsJacobian.

this = init_assembly(this, model, fun_test, fun_shape, symmetric )

