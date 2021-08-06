---
title : SlidingAirgap
parent: API
grand_parent : Documentation
---
## Summary
SlidingAirgap Sliding airgap model for radial-flux machines.
## PROPERTIES
* SlidingAirgap/displacement_function is a property.

* SlidingAirgap/n_bnd_moving is a property.

* SlidingAirgap/n_bnd_static is a property.

* SlidingAirgap/rotor_angle_now is a property.

* SlidingAirgap/x_displacement is a property.

* SlidingAirgap/y_displacement is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SlidingAirgap Sliding airgap model for radial-flux machines.

### * compute_torque Torque computation method.

[Torque, Force] = compute_torque(this, solution)

### * SlidingAirgap/deprecated_init is a function.

### * SlidingAirgap/deprecated_triplot is a function.

### * SlidingAirgap/fluxplot is a function.
fluxplot(this, A, rotorAngle, potentials)

### * SlidingAirgap/get_AGmatrix is a function.
Sag = get_AGmatrix(this, rotorAngle, N, t, varargin)

### * SlidingAirgap/get_airgap_meshes is a function.
[msh_static, msh_moving] = get_airgap_meshes(this)

### * SlidingAirgap/get_interpolatedMatrix is a function.
[Sint, P] = get_interpolatedMatrix(this, rotorAngle)

### * SlidingAirgap/init is a function.
init(this, model, n_bnd_static, n_bnd_moving, varargin)

### * SlidingAirgap/p_virt is a function.
p_virt = p_virt(this)

### * set_dynamic_eccentricity Set dynamic/general eccentricity.

set_dynamic_eccentricity(this, dfun), where dfun is a
function taking as arguments the rotor rotation angle (wm*t)
and timestamp t, and returning a 2x1 vector of the rotor
displacement.

### * set_eccentricity Set constant static eccentricity.

set_eccentricity(this, x, y), where x,y = rotor displacement
in meters.

For dynamic/general eccentricity, see
this.set_dynamic_eccentricity.

### * SlidingAirgap/t_ag is a function.
[a, b, tag] = t_ag(this, rotorAngle, varargin)

### * SlidingAirgap/t_const is a function.
t_const = t_const(this)

### * SlidingAirgap/t_moving is a function.
t_moving = t_moving(this)

### * SlidingAirgap/tag_solution is a function.
A_tag = tag_solution(this, A, rotorAngle, use_fixed)

### * transform_force_to_stationary_frame Force transformation.

Fxy = transform_force_to_stationary_frame(this, F, rotor_angle)
transforms the force F from rotor coordinates (rotor at angle
rotor_angle (mech. rad)) to stator coordinates.

### * SlidingAirgap/update_rotor_position is a function.
update_rotor_position(this, rotorAngle, t)

