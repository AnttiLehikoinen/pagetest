---
title : Quad
parent: API
grand_parent : Documentation
---
## Summary
Quad - (Not recommended) Numerically evaluate integral, adaptive Simpson quadrature
This MATLAB function tries to approximate the integral of function fun from a to
b to within an error of 1e-6 using recursive adaptive Simpson quadrature.
q = quad(fun,a,b)
q = quad(fun,a,b,tol)
q = quad(fun,a,b,tol,trace)
[q,fcnt] = quad(...)
See also dblquad, integral, integral2, integral3, quad2d, quadgk, quadl,
quadv, trapz, triplequad
## PROPERTIES
* Quad/mesh is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Quad/Quad is a constructor.
this = Quad(msh)

### * Quad/get_mapping is a function.
F = get_mapping(this, elements, x0)

