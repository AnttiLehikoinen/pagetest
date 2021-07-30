---
title : GeoParser
parent: API
grand_parent : Documentation
---
## Summary
GeoParser methods:
GeoParser - is a class.
closest_arc - GeoParser/closest_arc is a function.
closest_curve - curve_type
closest_line - GeoParser/closest_line is a function.
parse_split_curves - GeoParser/parse_split_curves is a function.
parse_surfaces - X = [24;15];
surface_at - FIXME Nested surfaces
## PROPERTIES
* GeoParser/curves is a property.

* GeoParser/outer_surfaces is a property.

* GeoParser/points is a property.

* GeoParser/surfaces is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * GeoParser/GeoParser is a constructor.

### * GeoParser/add_curve is a function.
add_curve(this, c)

### * GeoParser/add_point is a function.
add_point(this, p)

### * GeoParser/closest_arc is a function.
[c, Pc] = closest_arc(this, P)

### * curve_type

### * GeoParser/closest_line is a function.
[c, Pc] = closest_line(this, P)

### * GeoParser.from_dxf is a function.
this = from_dxf(fname)

### * GeoParser/parse_split_curves is a function.
parse_split_curves(this)

### * X = [24;15];
ainner_cand = this.closest_arc( X );

### * GeoParser/plot_curves is a function.
plot_curves(this, varargin)

### * GeoParser/remove_curve is a function.
remove_curve(this, c)

### * FIXME Nested surfaces

