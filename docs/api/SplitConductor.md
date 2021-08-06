---
title : SplitConductor
parent: API
grand_parent : Documentation
---
## Summary
SplitConductor methods:
SplitConductor - is a class.
set_matrices - SplitConductor/set_matrices is a function.
## PROPERTIES
* SplitConductor/domain_over_split is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SplitConductor/SplitConductor is a constructor.
this = SplitConductor(type, domain, domain_over_split)

### * SplitConductor/copy is a function.
c = copy(this)

### * SplitConductor/domains is a function.
ds = domains(this)

### * SplitConductor/electric_potential_at_nodes is a function.
U = electric_potential_at_nodes(this, u)

### * SplitConductor/elements is a function.
els = elements(this)

### * SplitConductor/integration_matrix is a function.
M = integration_matrix(this)

### * SplitConductor/losses is a function.
p = losses(this, dA, u, M)

### * SplitConductor/next_domain is a function.
[dnext, coeff] = next_domain(this)

### * SplitConductor/nodes is a function.
[n, n_first, n_next] = nodes(this)

### * SplitConductor/set_matrices is a function.
this = set_matrices(this, msh, M, C_Ai, C_au, CC_uu, sigma, column)

