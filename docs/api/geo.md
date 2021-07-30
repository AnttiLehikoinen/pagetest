---
title : geo
parent: API
grand_parent : Documentation
---
## Summary
enumeration
line
arc
hole
end
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * add_fillet Fillet intersection of two lines

P = add_fillet(r, pa1, pa2, pb1, pb2, varargin)

P = add_fillet(r, pa1, pa2, pb1, pb2, direction)

### * geo.arc is a function.
e = arc

### * geo.closest_point is a function.
pclosest = closest_point(X, points)

### * geo.find_arc is a function.
[l, direction] = find_arc(p1, pc, p2)

### * find_line Find line between two points.

[l, direction] = find_line(p1, p2)

### * enumeration
line
arc
hole
end

### * geo.hole is a function.
e = hole

### * LINE Create line
LINE(X,Y) adds the **line** defined in vectors X and Y to the current axes.
If X and Y are matrices of the same size, **line** draws one **line** per
column.

LINE(X,Y,Z) creates lines in three-dimensional coordinates.

LINE('XData',x,'YData',y,'ZData',z,...) creates a **line** in the current
axes using the Name,Value pairs as arguments. This is the low-level
form of the **line** function, which does not accept matrix coordinate data
as the other informal forms described above.

LINE(...,Name,Value) specifies **line** properties using one or more
Name,Value pair arguments.

LINE(container,...) creates the **line** in the axes, group, or transform
specified by container, instead of in the current axes.

H = LINE(...)  returns a column vector of the primitive **line** objects
created.

Execute GET(H), where H is a **line** object, to see a list of **line** object
properties and their current values.
Execute SET(H) to see a list of **line** object properties and legal
property values.

See also PATCH, TEXT, PLOT, PLOT3.

### * geo.parse_named is a function.
C = parse_named(entities)

### * parsing start line

### * set_periodic Set two Lines as periodic.

The purpose of this method is to specify two Lines as
periodic, so that they are meshed in conforming fashion. The
method takes as arguments [Point](Point.html) objects ordered as follows:

set_periodic( P_start_1, P_end_1, P_start_2, P_end_2), where

* P_start_1, P_end_1 belong to the first Line/boundary.

* P_start_2, P_end_2 belong to the second boundary.

* Ordering is consistent, e.g. Point_1_start -->
Point_1_end and Point_2_start --> Point_2_end are both
radially oriented.

* By default, Line 1 must be on the 'clockwise' boundary: actual
clockwise boundary for radial-flux geometries, positive-x
for linear/sliced axial geometries. For further use, Line 1
will be named 'n_cw', and Line 2 as 'n_ccw'. To ignore this condition
and skip renaming use the call syntax:

set_periodic( P_start_1, P_end_1, P_start_2, P_end_2, true)

