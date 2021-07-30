---
title : SheetCircuit
parent: API
grand_parent : Documentation
---
## Summary
SheetCircuit is a class.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * SheetCircuit/SheetCircuit is a constructor.

### * init Initialize matrices etc. for circuit.

init(this, problem) ties this to the given [MagneticsProblem](MagneticsProblem.html) and
initializes the problem matrices and arrays in this.matrices:

* inds_solid : which of the Conductors in this are solid

* inds_stranded : likewise for stranded

* R : per-conductor resistances, active length

* R_EW : per-conductor resistances, end-winding length

* area : conductor areas

* sigma : conductor conductivities. Assumed uniform.

* M : mass/damping matrix

* C_Ai : current source matrix

* C_Au : voltage source matrix

* C_uu : voltage-voltage coupling matrix

* L : circuit loop matrix
Help for SheetCircuit/init is inherited from superclass CIRCUIT

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
Help for SheetCircuit/losses is inherited from superclass CIRCUITBASE

### * SheetCircuit/parse_v11 is a function.
[conductor, name] = parse_v11(this)

