---
title : AxialGeometryExtruder
parent: API
grand_parent : Documentation
---
## Summary
AxialGeometryExtruder methods:
AxialGeometryExtruder - is a class.
extrude - AxialGeometryExtruder/extrude is a function.
extrude_flat - AxialGeometryExtruder/extrude_flat is a function.
extrude_surface_along_symmetry_boundary - AxialGeometryExtruder/extrude_surface_along_symmetry_boundary is a function.
initialize_3D_points - AxialGeometryExtruder/initialize_3D_points is a function.
transform_initial_points - AxialGeometryExtruder/transform_initial_points is a function.
## PROPERTIES
* AxialGeometryExtruder/sector_angle is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * AxialGeometryExtruder/AxialGeometryExtruder is a constructor.
this = AxialGeometryExtruder(geometry, r, a)

### * AxialGeometryExtruder/extrude is a function.
Vs = extrude(this, domain, level)

### * AxialGeometryExtruder/extrude_flat is a function.
Vs = extrude_flat(this, domain, level, a)

### * AxialGeometryExtruder/extrude_point_along_symmetry_boundary is an undocumented builtin AxialGeometryExtruder method.

### * AxialGeometryExtruder/extrude_surface_along_symmetry_boundary is a function.
extrude_surface_along_symmetry_boundary(this, surface, r)

### * AxialGeometryExtruder/finalize_initial_surface is a function.
finalize_initial_surface(this, snew)

### * GET    Get object properties.
V = GET(H,'PropertyName') returns the value of the specified property
for the graphics object with handle H.  If H is a vector of handles,
then **get** will return an M-by-1 cell array of values where M is equal
to length(H).  If 'PropertyName' is replaced by a 1-by-N or N-by-1 cell
array of strings containing property names, then GET will return an
M-by-N cell array of values.

GET(H) displays the names and current values of all user-gettable
properties for the graphics object with handle H.

V = GET(H) where H is a scalar, returns a structure where each field
name is the name of a user-gettable property of H and each field
contains the value of that property.

V = GET(0, 'Factory')
V = GET(0, 'Factory[ObjectType](ObjectType.html)')
V = GET(0, 'Factory[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)')
returns for all object types the factory values of all properties
which have user-settable default values.

V = GET(H, 'Default')
V = GET(H, 'Default[ObjectType](ObjectType.html)')
V = GET(H, 'Default[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)')
returns information about default property values (H must be scalar).
'Default' returns a list of all default property values currently set
on H.  'Default[ObjectType](ObjectType.html)' returns only the defaults for properties
of [ObjectType](ObjectType.html) set on H.
'Default[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)' returns the default value for the
specific property, by searching the defaults set on H and its
ancestors, until that default is found.  If no default value for this
property has been set on H or any ancestor of H up through the root,
then the factory value for that property is returned.

Defaults can not be queried on a descendant of the object, or on the
object itself - for example, a value for 'DefaultAxesColor' can not
be queried on an axes or an axes child, but can be queried on a figure
or on the root.

When using the 'Factory' or 'Default' GET, if PropertyName is omitted
then the return value will take the form of a structure in which each
field name is a property name and the corresponding value is the value
of that property.  If PropertyName is specified then a matrix or string
value will be returned.


See also SET, RESET, DELETE, GCF, GCA, FIGURE, AXES.

### * AxialGeometryExtruder/initialize_3D_points is a function.
initialize_3D_points(this)

### * AxialGeometryExtruder/plot_curves is a function.
plot_curves(this, varargin)

### * AxialGeometryExtruder/plot_points is a function.
plot_points(this, varargin)

### * AxialGeometryExtruder/transform_initial_points is a function.
transform_initial_points(this, r)

