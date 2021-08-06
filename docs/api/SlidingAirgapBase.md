---
title : SlidingAirgapBase
parent: API
grand_parent : Documentation
---
## Summary
SlidingAirgapBase methods:
SlidingAirgapBase - is a class.
compute_torque - Torque computation method.
drawFluxLines - SlidingAirgapBase.drawFluxLines is a function.
fluxplot - SlidingAirgapBase/fluxplot is a function.
get_interpolatedMatrix - SlidingAirgapBase/get_interpolatedMatrix is a function.
triplot - SlidingAirgapBase/triplot is a function.
## PROPERTIES
* SlidingAirgapBase/P_fixed is a property.

* SlidingAirgapBase/Sconst is a property.

* SlidingAirgapBase/Sint is a property.

* SlidingAirgapBase/angle_multiplier is a property.

* SlidingAirgapBase/is_constant is a property.

* SlidingAirgapBase/le_fixed is a property.

* SlidingAirgapBase/le_fixed_single is a property.

* SlidingAirgapBase/le_int is a property.

* SlidingAirgapBase/model is a property.

* SlidingAirgapBase/moving_component is a property.

* SlidingAirgapBase/n_fixed is a property.

* SlidingAirgapBase/n_int is a property.

* SlidingAirgapBase/r_int is a property.

* SlidingAirgapBase/static_component is a property.

* SlidingAirgapBase/t_fixed is a property.

* SlidingAirgapBase/t_int is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SlidingAirgapBase/SlidingAirgapBase is a constructor.

### * SlidingAirgapBase/compute_stiffness_matrices is a function.
compute_stiffness_matrices(this)

### * compute_torque Torque computation method.

[Torque, Force] = compute_torque(this, solution)

### * drawFluxLines Draws flux lines.

drawFluxLines(msh, A, Nl, args) draws a total of Nl flux lines with the
"plot" function and input arguments args

If the mesh struct msh has a field "rotel", the call syntax can be
drawFluxLines(msh, A, Nl, rotorAngle, args)

Copyright (c) 2016 Antti Lehikoinen / Aalto University

### * SlidingAirgapBase/fluxplot is a function.
fluxplot(this, A, rotorAngle, potentials)

### * SlidingAirgapBase/get_airgap_meshes is a function.
[msh_static, msh_moving] = get_airgap_meshes(this)

### * SlidingAirgapBase/get_interpolatedMatrix is a function.
[Sint, P] = get_interpolatedMatrix(this, rotorAngle)

### * transform_force_to_stationary_frame Force transformation.

Fxy = transform_force_to_stationary_frame(this, F, rotor_angle)
transforms the force F from rotor coordinates (rotor at angle
rotor_angle (mech. rad)) to stator coordinates.

### * TRIPLOT Plots a 2D triangulation
TRIPLOT(TRI,X,Y) displays the triangles defined in the
M-by-3 matrix TRI.  A row of TRI contains indices into X,Y that
define a single triangle. The default line color is blue.

TRIPLOT(TR) displays the triangles in the triangulation TR.

TRIPLOT(...,COLOR) uses the string COLOR as the line color.

H = TRIPLOT(...) returns a line handle representing the displayed
triangles edges.

TRIPLOT(...,'param','value','param','value'...) allows additional
line param/value pairs to be used when creating the plot.

Example 1:
X = rand(10,2);
dt = delaunayTriangulation(X);
triplot(dt)

Example 2:
% Plotting a Delaunay triangulation in face-vertex format
X = rand(10,2);
dt = delaunayTriangulation(X);
tri = dt(:,:);
triplot(tri, X(:,1), X(:,2));

See also TRISURF, TRIMESH, DELAUNAY, triangulation, delaunayTriangulation.

### * SlidingAirgapBase/update_rotor_position is a function.
update_rotor_position(this, rotorAngle, t)

