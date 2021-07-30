---
title : Line
parent: API
grand_parent : Documentation
---
## Summary
Line methods:
Line - is a class.
from_points - Create an Line from Points.
## PROPERTIES
* type - Type (geo.line or geo.arc)
Help for Line.type is inherited from superclass CURVE

## Methods
Class methods are listed below. Inherited methods are not included.
### * Line/Line is a constructor.
this = Line(pstart, pend)

### * length Line length.

### * from_points Create an Line from Points.

this = from_points(pstart, pend) either creates a new Line, or
returns an existing Line if found.

this = from_points(pstart, pend, false) returns an existing Line,
or throws an error if not found.

### * uminus Reverse direction, return a new Curve.

