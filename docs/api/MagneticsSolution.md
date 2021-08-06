---
title : MagneticsSolution
parent: API
grand_parent : Documentation
---
## Summary
MagneticsSolution Class for representing the solution to MagneticsProblem.


WARNING: Doing

sol_1 = problem.solve_xx();

sol_2 = problem.solve_xx();

results = do_something(sol_1)

may cause unexpected results. Please use solutions right away.
## PROPERTIES
* data - any other data, struct

* dof_map - mapping for indices etc.

* parameters -  [SimulationParameters](SimulationParameters.html) associated with the solution

* problem -  [MagneticsProblem](MagneticsProblem.html) associated with the solution

* raw_solution - raw solution array

* MagneticsSolution.type is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * MagneticsSolution Class for representing the solution to MagneticsProblem.


WARNING: Doing

sol_1 = problem.solve_xx();

sol_2 = problem.solve_xx();

results = do_something(sol_1)

may cause unexpected results. Please use solutions right away.

### * MagneticsSolution/get_dof is a function.
val = get_dof(this, key)

### * indices_to_last_period Return indices to solution over the last
electrical period.

### * MagneticsSolution/set_dof is a function.
set_dof(this, key, val)

