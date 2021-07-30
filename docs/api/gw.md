---
title : gw
parent: API
grand_parent : Documentation
---
## Summary
gw methods:
gw - is a class.
initialize - adding surfaces
loadmesh - opening file
write_file - gw/write_file is a function.
## PROPERTIES
* gw/fname is a property.

* gw/lcar is a property.

* gw/lineloops is a property.

* gw/lines is a property.

* gw/points is a property.

* gw/surfaces is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * gw/generate_mesh is a function.
generate_mesh(this)

### * gw/gw is a constructor.
this = gw(varargin)

### * adding surfaces

### * opening file

### * MESH   3-D **mesh** surface.
MESH(X,Y,Z,C) plots the colored parametric **mesh** defined by
four matrix arguments.  The view point is specified by VIEW.
The axis labels are determined by the range of X, Y and Z,
or by the current setting of AXIS.  The color scaling is determined
by the range of C, or by the current setting of CAXIS.  The scaled
color values are used as indices into the current COLORMAP.

MESH(X,Y,Z) uses C = Z, so color is proportional to **mesh** height.

MESH(x,y,Z) and MESH(x,y,Z,C), with two vector arguments replacing
the first two matrix arguments, must have length(x) = n and
length(y) = m where [m,n] = size(Z).  In this case, the vertices
of the **mesh** lines are the triples (x(j), y(i), Z(i,j)).
Note that x corresponds to the columns of Z and y corresponds to
the rows.

MESH(Z) and MESH(Z,C) use x = 1:n and y = 1:m.  In this case,
the height, Z, is a single-valued function, defined over a
geometrically rectangular grid.

MESH(...,'PropertyName',PropertyValue,...) sets the value of
the specified surface property.  Multiple property values can be set
with a single statement.

MESH(AX,...) plots into AX instead of GCA.

MESH returns a handle to a surface plot object.

AXIS, CAXIS, COLORMAP, HOLD, SHADING, HIDDEN and VIEW set figure,
axes, and surface properties which affect the display of the mesh.

See also SURF, MESHC, MESHZ, WATERFALL.

### * gw/write_file is a function.
this = write_file(this, varargin)

