---
title : MotorModelBase
parent: API
grand_parent : Documentation
---
## Summary
MotorModelBase Base class for magnetics models.

Default construction:

motor = MotorModelBase(dimensions, stator, rotor), with

* dimensions : struct

* stator : a [StatorBase](StatorBase.html) object

* rotor : a rotor / [GeoBase](GeoBase.html) object

Detailed construction:

motor = MotorModelBase(dimensions);

motor.add_component(c1, component_name);

motor.add_component(c2, component_name);

motor.add_component(c3, component_name);

motor.add_airgap(static_part, moving_part);

motor.set_outer_boundary(bnd);

motor.finalize();
## PROPERTIES
* MotorModelBase/Ne_component is a property.

* MotorModelBase/Np_component is a property.

* PMs - permanent magnets

* airgap - **airgap** container

* MotorModelBase/boundaries is a property.

* circuits - circuits

* components - geometries making up this

* materials - materials

* MotorModelBase/mesh is a property.

* MotorModelBase/periodicityCoeff is a property.

* MotorModelBase/ri_component is a property.

* rotor - array of moving components

* stator - array of static components

* MotorModelBase/symmetrySectors is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * MotorModelBase Base class for magnetics models.

Default construction:

motor = MotorModelBase(dimensions, stator, rotor), with

* dimensions : struct

* stator : a [StatorBase](StatorBase.html) object

* rotor : a rotor / [GeoBase](GeoBase.html) object

Detailed construction:

motor = MotorModelBase(dimensions);

motor.add_component(c1, component_name);

motor.add_component(c2, component_name);

motor.add_component(c3, component_name);

motor.add_airgap(static_part, moving_part);

motor.set_outer_boundary(bnd);

motor.finalize();

### * MotorModelBase/add_component is a function.
add_component(this, name, component, varargin)

### * add_gap Add airgap.

See AirgapContainer.add_gap

### * compute_torque Computes torque

T = compute_torque(this, solution)

Computes torque associated with the MagneticsSolution
solution.

T is of size number_of_airgaps x number_of_steps

### * finalizing mesh part

### * MotorModelBase/get_AGmatrix is a function.
S = get_AGmatrix(this, rotorAngle, varargin)

### * MotorModelBase/global_element_indices is a function.
is = global_element_indices(this, is, component)

### * MotorModelBase/global_node_indices is a function.
ns = global_node_indices(this, ns, component)

### * MotorModelBase/initialize_airgap is a function.
initialize_airgap(this)

### * MotorModelBase/mass is a function.
[m, m_domain, m_mat] = mass(this)

### * plot_flux Plot flux density.

plot_flux(this, solution)

plot_flux(this, solution, steps_to_plot)

### * results_summary Summary of analysis results.

results = results_summary(this, solution) returns a structure.

results_summary(this, solution) prints the summary to command prompt.

results = results_summary(this, solution, 'verbose', true) returns a
structure AND prints the results to the command line.

The output (structure) contains information like input and output power,
summary of stator.winding terminal quantities, sum and breakdown of iron
losses, and sum and breakdown of losses in all circuits / conducting
bodies.

Interesting output quantities include:

* torque_mean : Mean torque (radial-flux only)

* shaft_power : radial-flux only

* total_losses : self-evident

* efficiency : from shaft power and total losses

* input_power_from_power_balance : shaft power plus total losses

* input_power_from_terminal_waveforms : Does not contain post-processed
loss quantities (typically iron losses, some non-enabled circuits).

### * MotorModelBase/rotel is a function.
els = rotel(this)

### * set_outer_boundary Set outer boundary.

set_outer_boundary(this, bnd_1, bnd_2, ...)

Set the given [Boundary](Boundary.html) objects as outer (flux insulation)
boundaries.

### * VISUALIZE Visualize geometry.

visualize(this, key, val), with:

* 'linestyle' : line style for mesh. Default 'none'

* 'plot_ag' : plot airgap mesh. Default false.

* 'plot_axial' : plot axial view. Default false.

* 'plot_nodes' : plot boundary nodes. Default false.

### * MotorModelBase/visualize_axial is a function.
visualize_axial(this, varargin)

### * MotorModelBase/visualize_radial is a function.
visualize_radial(this, varargin)

