---
title : Circuit
parent: API
grand_parent : Documentation
---
## Summary
Circuit Simple base class for circuits modelled with the AVI
formulation.
## PROPERTIES
* Circuit/f is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Circuit Constructor.

### * Circuit/compute_conductor_areas is a function.
compute_conductor_areas(this)

### * get_loop_matrix EW resistance matrix.

### * Circuit/get_cc_blocks is a function.
[Scc, Mcc] = get_cc_blocks(this, problem, type)

### * get_loop_matrix Loop matrix associated with the circuit.

### * get_matrices Get circuit matrices for a particular problem

### * get_ndof Number of dofs associated with the circuit, for the given
problem and type.

Nui = get_ndof(this, problem, type, pars), where

* problem = [MagneticsProblem](MagneticsProblem.html) or similar

* type = string, usually "static" / "harmonic" / "stepping"
Help for Circuit/get_ndof is inherited from superclass CIRCUITBASE

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

### * init_for_simulation Init Circuit for simulation.

init_for_simulation(this, problem, type, pars)
Help for Circuit/init_for_simulation is inherited from superclass CIRCUITBASE

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
Help for Circuit/losses is inherited from superclass CIRCUITBASE

### * set_load1 Set load vector.

Has no effect.

### * set_source Set circuit source.

set_source(this, varargin{:})

Has no effect. Must be subclassed.

