---
title : NodalBoundaryMatrix
parent: API
grand_parent : Documentation
---
## Summary
NodalBoundaryMatrix methods:
NodalBoundaryMatrix - is a class.
finalize - getting free nodes
from_mesh - NodalBoundaryMatrix.from_mesh is a function.
## PROPERTIES
* NodalBoundaryMatrix/Nrows is a property.

* NodalBoundaryMatrix/dirichlet_boundaries is a property.

* NodalBoundaryMatrix/interpolated_parts is a property.

* NodalBoundaryMatrix/mesh is a property.

* NodalBoundaryMatrix/new_node_indices is a property.

* NodalBoundaryMatrix/nonzero_elements is a property.

* NodalBoundaryMatrix/periodic_boundaries is a property.

* NodalBoundaryMatrix/periodicity_coefficient is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * NodalBoundaryMatrix/NodalBoundaryMatrix is a constructor.
this = NodalBoundaryMatrix(msh)

### * NodalBoundaryMatrix/add_Diriclet_boundary is a function.
add_Diriclet_boundary(this, bnd)

### * NodalBoundaryMatrix/add_interpolated_part is a function.
add_interpolated_part(this, P)

### * NodalBoundaryMatrix/add_nonzero_elements is a function.
add_nonzero_elements(this, els)

### * NodalBoundaryMatrix/add_periodic_boundary is a function.
add_periodic_boundary(this, bnd, coeff)

### * getting free nodes

### * NodalBoundaryMatrix.from_mesh is a function.
P = from_mesh(msh, periodicity_coefficient)

