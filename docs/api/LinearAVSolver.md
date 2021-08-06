---
title : LinearAVSolver
parent: API
grand_parent : Documentation
---
## Summary
LinearAVSolver methods:
LinearAVSolver - is a class.
compute_preconditioner - LinearAVSolver/compute_preconditioner is a function.
compute_problem_matrices - LinearAVSolver/compute_problem_matrices is a function.
save_problem - LinearAVSolver/save_problem is a function.
solve - LinearAVSolver/solve is a function.
## PROPERTIES
* LinearAVSolver/F is a property.

* LinearAVSolver/L is a property.

* LinearAVSolver/M is a property.

* LinearAVSolver/P_edges is a property.

* LinearAVSolver/P_nodes is a property.

* LinearAVSolver/Pleft is a property.

* LinearAVSolver/Pright is a property.

* LinearAVSolver/S is a property.

* LinearAVSolver/alpha1 is a property.

* LinearAVSolver/alpha2 is a property.

* LinearAVSolver/current_solution is a property.

* LinearAVSolver/dt is a property.

* LinearAVSolver/is_boundary_modified is a property.

* LinearAVSolver/is_lhs_modified is a property.

* LinearAVSolver/lhs is a property.

* LinearAVSolver/order is a property.

* LinearAVSolver/previous_solution is a property.

* LinearAVSolver/rhs is a property.

* LinearAVSolver/scale is a property.

* LinearAVSolver/step is a property.

* LinearAVSolver/tolerance is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * LinearAVSolver/LinearAVSolver is a constructor.
this = LinearAVSolver(varargin)

### * LinearAVSolver/compute_preconditioner is a function.
compute_preconditioner(this)

### * LinearAVSolver/compute_problem_matrices is a function.
compute_problem_matrices(this)

### * LinearAVSolver/save_problem is a function.
save_problem(this)

### * LinearAVSolver/set_damping is a function.
set_damping(this, M)

### * LinearAVSolver/set_edge_boundary_matrix is a function.
set_edge_boundary_matrix(this, Pe)

### * LinearAVSolver/set_nodal_boundary_matrix is a function.
set_nodal_boundary_matrix(this, Pn)

### * LinearAVSolver/set_rhs is a function.
set_rhs(this, F)

### * LinearAVSolver/set_step is a function.
set_step(this, k)

### * LinearAVSolver/set_stiffness is a function.
set_stiffness(this, S)

### * LinearAVSolver/solve is a function.
x = solve(this)

