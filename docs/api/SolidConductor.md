---
title : SolidConductor
parent: API
grand_parent : Documentation
---
## Summary
SolidConductor methods:
SolidConductor - is a class.
set_matrices - SolidConductor/set_matrices is a function.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * SolidConductor/SolidConductor is a constructor.
this = SolidConductor(varargin)

### * SolidConductor/copy is a function.
c = copy(this)

### * SolidConductor/electric_potential_at_nodes is a function.
U = electric_potential_at_nodes(this, u)

### * SolidConductor/elements is a function.
els = elements(this)

### * SolidConductor/integration_matrix is a function.
M = integration_matrix(this)

### * SolidConductor/nodes is a function.
n = nodes(this)

### * SolidConductor/set_matrices is a function.
this = set_matrices(this, msh, M, C_Ai, C_au, CC_uu, sigma, column)

