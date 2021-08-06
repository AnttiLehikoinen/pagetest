---
title : Curve
parent: API
grand_parent : Documentation
---
## Summary
CURVE Abstract base class for representing line segments and circle arcs
## PROPERTIES
* Curve/left_surface is a property.

* name - name, Optional

* pcenter - Center [Point](Point.html) of Arc.

* pend - end  [Point](Point.html) of curve

* periodic_with - Another curve that *this*  is periodic with.

* pstart - start [Point](Point.html) of curve

* Curve/right_surface is a property.

* type - Type (geo.line or geo.arc)

* Curve/xend is a property.

* Curve/xstart is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Constructor

this = Curve(pstart, pend)

Create a line segment (geo.line) between the [Point](Point.html)
objects.
pstart and pend.

this = Curve(pstart, pcenter, pend)

Create a circle arc (geo.arc) between pstart and pend, centered at
pcenter.

### * add_to_points Add this to defining Points.

### * angle Angle between two Curves.

Call syntax

a = c1.angle(c2)

a = angle(c1, c2)

Returns the **angle** a.

### * Curve/center is a function.
pc = center(this)

### * Curve/detach is a function.
detach(this)

### * Curve/distance_from_point is a function.
[d, Pclosest] = distance_from_point(this, P)

### * == (EQ)   Test handle equality.
Handles are equal if they are handles for the same object.

H1 == H2 performs element-wise comparisons between handle arrays H1 and
H2.  H1 and H2 must be of the same dimensions unless one is a scalar.
The result is a logical array of the same dimensions, where each
element is an element-wise equality result.

If one of H1 or H2 is scalar, scalar expansion is performed and the
result will match the dimensions of the array that is not scalar.

TF = EQ(H1, H2) stores the result in a logical array of the same
dimensions.

See also CURVE, CURVE/GE, CURVE/GT, CURVE/LE, CURVE/LT, CURVE/NE
Help for Curve/eq is inherited from superclass HANDLE

### * Direction of this Curve to join with other curve.

ldir = extend_direction(this, other_curve)

### * extends Check if this Curve **extends** other curve.

bl = extends(this, other_curve, other_curve_direction)

### * get_xy Get xy-coordinates of start- and end-points.

### * joinable_with Check if this Curve joins with other Curve.

bl = joinable_with(this, other_line)

bl = true if this shares a point with other_line

### * ~= (NE)   Not equal relation for handles.
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

See also CURVE, CURVE/EQ, CURVE/GE, CURVE/GT, CURVE/LE, CURVE/LT
Help for Curve/ne is inherited from superclass HANDLE

### * Curve/next_left is a function.
l = next_left(this, P)

### * norm Length of Curve.

### * plot Plot Curve.

### * Curve/points is a function.
X = points(this)

### * rotate Rotate around the origin, return a new Curve.

### * Curve/split_with_point is a function.
new_curve = split_with_point(this, P)

### * Curve/tangent is a function.
t = tangent(this, p)

