---
title : AxialGeometry
parent: API
grand_parent : Documentation
---
## Summary
AxialGeometry methods:
AxialGeometry - is a class.
visualize_radial - AxialGeometry/visualize_radial is a function.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * AxialGeometry/AxialGeometry is a constructor.

### * copy_domain Copy domain and apply necessary rotations or
translations.

new = copy_domain(this, old_domain, sector_shift)

DEFAULT behaviour: rotate domain remanence and orientation
directions, if any, by sector_shift.

### * mesh_elementary_geometry Create mesh for the elementary geometry.

mesh_elementary_geometry(this)

Meshes the *elementary*  geometry, e.g. the raw geometry before possible
replication.

Note that the methods `this.shift_elementary_nodes` ,
`this.copy_domain` , and `this.parse_nodes`  have to be implemented.
Help for AxialGeometry/mesh_elementary_geometry is inherited from superclass GEOBASE

### * this = parse_nodes@GeoBase(this, Surfaces);

### * shift_elementary_nodes Apply symmetry shift.

### * AxialGeometry/visualize_radial is a function.
visualize_radial(this, varargin)

### * y_shift_points Shift all [Point](Point.html) objects of this in
y-direction.

y_shift_points(this, shift)

### * y_shift_points Shift all [Point](Point.html) objects of this in
y-direction.

y_shift_points(this, shift)

### * y_shift_points Shift all [Point](Point.html) objects of this in
y-direction.

y_shift_points(this, shift)

