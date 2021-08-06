---
title : LinearSlidingAirgap
parent: API
grand_parent : Documentation
---
## Summary
LinearSlidingAirgap Airgap class for sliced AFM models.

[] FIXME set slice radius at constructor, break dependence on
AFmodel2
## PROPERTIES
* LinearSlidingAirgap/mult is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * LinearSlidingAirgap Airgap class for sliced AFM models.

[] FIXME set slice radius at constructor, break dependence on
AFmodel2

### * return

### * LinearSlidingAirgap/get_AGmatrix is a function.
Sag = get_AGmatrix(this, rotorAngle, varargin)

### * LinearSlidingAirgap/get_airgap_meshes is a function.
[msh_static, msh_moving] = get_airgap_meshes(this)

### * LinearSlidingAirgap/init is a function.
init(this, model, n_bnd_static, n_bnd_moving, varargin)

### * drawFluxLines Draws flux lines.

### * LinearSlidingAirgap/p_virt is a function.
p_virt = p_virt(this)

### * LinearSlidingAirgap/t_ag is a function.
[a, b, tag] = t_ag(this, rotorAngle, varargin)

### * LinearSlidingAirgap/t_const is a function.
t_const = t_const(this)

### * LinearSlidingAirgap/t_moving is a function.
t_moving = t_moving(this)

### * LinearSlidingAirgap/tag_solution is a function.
A_tag = tag_solution(this, A, rotorAngle, use_fixed)

### * transform_force_to_stationary_frame Force transformation.

Fxy = transform_force_to_stationary_frame(this, F, rotor_angle)
transforms the force F from rotor coordinates (rotor at angle
rotor_angle (mech. rad)) to stator coordinates.

