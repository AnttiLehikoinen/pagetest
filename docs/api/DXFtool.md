---
title : DXFtool
parent: API
grand_parent : Documentation
---
## Summary
DXFtool v1.0 for reading and plotting DXF files in Matlab figures.
by M.M. Pedersen, Aarhus University, March 2018.

USAGE:    dxf = DXFtool('filename.dxf');
plots dxf file in current axes/figure
(or creates a new figure/axes if none exist)

INPUT:    filename of dxf file as a string (may also include path)

OUTPUT:   [optional] dxf object. Each entity is stored in a struct
in dxf.entites(i), where i is the entity number,
containing the following fields:
.name:      entity type name (string), code 0
.layer:     Layer name (string), code 8
.linetype:  Line dashing type (string), code 6
.color:     Line color (int), code 62
.closed:    polygon status: open/closed, code 70
.point:     Xp, Yp
.poly:      vertices X,Y array [n_verts,2]
.arc:       Xc, Yc, R, begin angle, end angle
.circle:    Xc, Yc, R
.ellipse:   Xc, Yc, Xe, Ye, ratio, begin angle, end angle
.line:      X1, Y1, X2, Y2
.hatch:     color data for closed polygons
.handle:    Matlab graphics handle to plotted entity

FEATURES:
- supports: LINE, POINT, ARC, CIRCLE, ELLIPSE, LWPOLYLINE
- colored entities (line and hatch color)
- respects ordering of objects (back to front)
- supports bulges, open/closed polygons
- line dashing

TODO:
- more entities: DIMENSION, 3D...
- propor handling of splines (currently piecewise linear)
- line weight


Some modifications by Antti Lehikoinen / Smeklab Ltd, 2021.
## PROPERTIES
* divisions -  points along nonlinear entities (circles, arcs, bulges, ellipses)

* entities -  struct array of entities

* filename -  path/filename of DXF file

* ~= (NE)   Not equal relation for handles.
Handles are equal if they are handles for the same object and are
unequal otherwise.

H1 ~= H2 performs element-wise comparisons between handle arrays H1
and H2.  H1 and H2 must be of the same dimensions unless one is a
scalar.  The result is a logical array of the same dimensions, where
each element is an element-wise equality result.

If one of H1 or H2 is scalar, scalar expansion is performed and the
result will match the dimensions of the array that is not scalar.

TF = NE(H1, H2) stores the result in a logical array of the same
dimensions.

See also DXFTOOL, DXFTOOL/EQ, DXFTOOL/GE, DXFTOOL/GT, DXFTOOL/LE, DXFTOOL/LT
Help for DXFtool/ne is inherited from superclass HANDLE
Documentation for DXFtool/ne
doc handle.ne

## Methods
Class methods are listed below. Inherited methods are not included.
### * construct dxf object

### * DXFtool/list is a function.
list(dxf)

### * getting **plot** started

