---
title : MagneticsProblem
parent: API
grand_parent : Documentation
---
## Summary
MagneticsProblem Class for solving magnetics problems.

this = MagneticsProblem( model )

Construct problem, where *model*  is an instance of RFmodel or
MotorModelBase class.

Main methods:

* solve_static : solve static problem with no damping effects.

* solve_harmonic : solve harmonic problem.

* solve_stepping : solve time-stepping problem.
## PROPERTIES
* model - The [MotorModelBase](MotorModelBase.html) (or compatible) **model** class associated with the problem

## Methods
Class methods are listed below. Inherited methods are not included.
### * MagneticsProblem Class for solving magnetics problems.

this = MagneticsProblem( model )

Construct problem, where *model*  is an instance of RFmodel or
MotorModelBase class.

Main methods:

* solve_static : solve static problem with no damping effects.

* solve_harmonic : solve harmonic problem.

* solve_stepping : solve time-stepping problem.

### * MagneticsProblem/get_component_property is a function.
prob = get_component_property(this, component, property, pars)

### * MagneticsProblem/set_boundary_matrix is a function.
this = set_boundary_matrix(this, varargin)

### * setting PM sources, if any

### * solve_harmonic Harmonic solution of a MagneticsProblem.

Solves a Harmonic magnetics problem, with sinusoidal time-variations.

solution = solve_harmonic(this, pars), where

* pars : a SimulationParameters object

* solution : a HarmonicSolution object.

Note: setting pars.isDC = true is recommended for synchronous machines;
in this case the rotor is rotated by 90 electrical degrees for the
imaginary/sinusoid component of the solution, compared to the
real/cosinusoid part. This provides an approximation of the effect of
rotor saliency.

NOTE: The real and imaginary fields **are**  coupled in the rotor, which is
incorrect for synchronous machines (as f_rotor = 0). As a result, the rotor
reluctivity gets overestimated. This may be fixed in a future release. In
the meantime, see MagneticsProblen.solve_quasistatic.

### * solve_quasistatic Quasi-static a MagneticsProblem.

Almost like solve_harmonic with the 'isDC' parameter set to true; but
only damping-related coupling between the d- and q-axes.

NOTE: Will probably be merged into solve_harmonic in the future.

### * solve_static Static solution of a MagneticsProblem.

Solves a static magnetics problem, with no damping effects.

solution = solve_static(this, pars), where

* pars : a SimulationParameters object

* solution : a StaticSolution object.

### * solve_stepping Time-stepping solution of a MagneticsProblem.

Solves a time-stepping problem.

solution = solve_harmonic(this, pars), where

* pars : a SimulationParameters object

* solution : a SteppingSolution object.

### * MagneticsProblem/sweep_harmonic is a function.
solutions = sweep_harmonic(this, pars)

