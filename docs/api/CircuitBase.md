---
title : CircuitBase
parent: API
grand_parent : Documentation
---
## Summary
CircuitBase Abstract base class for finite-element Circuits.

Use one of the subclasses to instantiate an object. Common examples
include

* [PolyphaseCircuit](PolyphaseCircuit.html)

* [BlockCircuit](BlockCircuit.html)

* [SheetCircuit](SheetCircuit.html)

* [ExtrudedBlockCircuit](ExtrudedBlockCircuit.html)

Use the `add_conductor`  method to add conductors to this.
## PROPERTIES
* CircuitBase/conductors is a property.

* CircuitBase/data is a property.

* enabled - FIXME persistence / consistence issues

* CircuitBase/is_time_invariant is a property.

* matrices - struct for containing circuit matrices

* CircuitBase/source is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * CircuitBase Abstract base class for finite-element Circuits.

Use one of the subclasses to instantiate an object. Common examples
include

* [PolyphaseCircuit](PolyphaseCircuit.html)

* [BlockCircuit](BlockCircuit.html)

* [SheetCircuit](SheetCircuit.html)

* [ExtrudedBlockCircuit](ExtrudedBlockCircuit.html)

Use the `add_conductor`  method to add conductors to this.

### * add_conductor Add conductor to circuit.

this = add_conductor(this, conductor, (type))

Adds the [Domain](Domain.html) or [Conductor](Conductor.html) object *conductor*  to this
Circuit. If *conductor*  is a Domain, a new Conductor object
is created.

Type is an optional arguments, either def.solid for a solid
conductor (default) or defs.stranded for stranded.

### * half_of_turn_length Return effective length.

### * filling_factor Conductor filling factor.

### * finalize_after_simulation Post-simulation callback function.

finalize_after_simulation(this, solution)

### * get_matrices Return FE-and circuit matrices.

[S, M, Sac, Mac, Sca, Mca, Scc, Mcc] = get_matrices(this,
problem, type), where

* S : stiffness-like FE matrix

* M : mass-FE matrix

* Sac : stiffness-like coupling from circuit variables to
FE variables.

* Mac : damping-like (d/dt) coupling from circuit variables to
FE variables.

* Sca : stiffness-like coupling from FE to circuit.

* Mca : damping-like coupling from FE to circuit.

* Scc : stiffness-like circuit-circuit coupling.

* Mcc : damping-like circuit-circuit coupling.

### * get_ndof Number of dofs associated with the circuit, for the given
problem and type.

Nui = get_ndof(this, problem, type, pars), where

* problem = [MagneticsProblem](MagneticsProblem.html) or similar

* type = string, usually "static" / "harmonic" / "stepping"

### * half_of_turn_length Return half of turn length.

Usually equal to `this.effective_length` , unless an
end-winding is modelled.

### * handle_latest_copies Object array method.

When called on an array of Circuit objects, this method calls
the `handle_latest_copies`  method on each individual Circuit.

### * handle_latest_copies1 Method for handling geometry
replication.

This method is called any time the elementary geometry is
replicated for a new sector/segment. By default, the latest
copies of the Domains associated with this circuit are added
as new Conductors.

This method works for a single Circuit object only, i.e. it
cannot be called on an object array. See
`this.handle_latest_copies`

### * indices_to_average_losses_over Indices for loss averaging.

inds = indices_to_average_losses_over(solution) returns

* the indices to the last period of the analysed solution
(solution.raw_solution(:, inds)
if strictly more than one period have been analysed.

* indices to the last 90 % of the analysed time, otherwise

### * init Init circuit for problem.

c = init(this, problem)

Returns:
c : Circuit-like object initialized for the problem.
Typically a handle to this.

### * init_for_simulation Init Circuit for simulation.

init_for_simulation(this, problem, type, pars)

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

### * set_load Increment load vector of FE problem.

F = set_load(this, F, type, varargin)

Add to load-contribution from this to F.

### * CircuitBase/set_parent is a function.
set_parent(this, parent)

