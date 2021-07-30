---
title : CageCircuit
parent: API
grand_parent : Documentation
---
## Summary
CageCircuit methods:
CageCircuit - is a class.
get_loop_matrix - TODO generalize dimensions
## PROPERTIES
* CageCircuit/broken_bars is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * CageCircuit/CageCircuit is a constructor.

### * CageCircuit/get_EW_impedance_matrix is a function.
Z = get_EW_impedance_matrix(this)

### * CageCircuit/get_EW_inductance_matrix is a function.
X = get_EW_inductance_matrix(this)

### * get_loop_matrix EW resistance matrix.
Help for CageCircuit/get_EW_resistance_matrix is inherited from superclass CIRCUIT

### * TODO generalize dimensions

### * losses Circuit losses.

[W_mean, loss_data] = losses(this, solution)

[W_mean, loss_data] = losses(this, solution, varargin), where

* W_mean : average total **losses** (W).

* loss_data : loss breakdowns and other data, depending on
CircuitBase subclass type. Structure.

By default, all loss information is computed for the entire
geometry, not just symmetry-section. This also applies to
per-conductor losses, so e.g. the **losses** in the "first damper
bar" actually mean "the sum of the **losses** in the first damper bar
of all poles".

For **losses** in typical 2D solid conductors (e.g. BlockCircuit,
SheetCircuit, CageCircuit), see compute_SolidConductorLosses.
Help for CageCircuit/losses is inherited from superclass CIRCUITBASE

