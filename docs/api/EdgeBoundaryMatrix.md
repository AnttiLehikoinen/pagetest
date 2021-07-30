---
title : EdgeBoundaryMatrix
parent: API
grand_parent : Documentation
---
## Summary
EdgeBoundaryMatrix methods:
EdgeBoundaryMatrix - is a class.
finalize - EdgeBoundaryMatrix/finalize is a function.
from_mesh - EdgeBoundaryMatrix.from_mesh is a function.
## PROPERTIES
* EdgeBoundaryMatrix/dirichlet_boundaries is a property.

* EdgeBoundaryMatrix/mesh is a property.

* EdgeBoundaryMatrix/periodic_boundaries is a property.

* EdgeBoundaryMatrix/periodicity_coefficient is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * EdgeBoundaryMatrix/EdgeBoundaryMatrix is a constructor.
this = EdgeBoundaryMatrix(msh)

### * EdgeBoundaryMatrix/add_Diriclet_boundary is a function.
add_Diriclet_boundary(this, bnd)

### * EdgeBoundaryMatrix/add_nonzero_elements is a function.
add_nonzero_elements(this, els)

### * EdgeBoundaryMatrix/add_periodic_boundary is a function.
add_periodic_boundary(this, bnd, coeff)

### * EdgeBoundaryMatrix/finalize is a function.
P = finalize(this, varargin)

### * EdgeBoundaryMatrix.from_mesh is a function.
P = from_mesh(msh, periodicity_coefficient)

