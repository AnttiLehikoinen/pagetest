---
title : BlockCircuit
parent: API
grand_parent : Documentation
---
## Summary
BlockCircuit is a class.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * BlockCircuit/BlockCircuit is a constructor.

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
Help for BlockCircuit/losses is inherited from superclass CIRCUITBASE

### * BlockCircuit/parse_v11 is a function.
[conductors, names] = parse_v11(this)

