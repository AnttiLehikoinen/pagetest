---
title : Surface
parent: API
grand_parent : Documentation
---
## Summary
SURFACE Class for representing elementary surfaces.

A Surface object represents a single surface with or without holes (i.e.
a simply or multiply connected surface). Each surface is defined by

* Its boundary. The boundary consists of segments, i.e. [Curve](Curve.html)
objects representing either a line segment or circle arc joining
two [Point](Point.html) objects.

* (Optional) Its holes, each a [Surface](Surface.html) themselves.

See <geometry_creation.html geometry creation> for more details.
## PROPERTIES
* holes - Array of [Surface](Surface.html) objects inside this Surface.

* Surface/is_closed is a property.

* line_directions - Direction of each boundary segment (+1 / -1).

* lines - Array of [Curve](Curve.html) objects defining the boundary of the geometry. Ordered.

* name - Surface name.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Surface Constructor.

this = Surface(name)

Create an empty surface with the specified name (string).

this = Surface(name, (Curve definitions))

Create a surface, and then pass all following arguments
(Curve definitions) to this.add_curve.

### * add_curve Add a curve to the surface boundary.

add_curve(this, geo.line, p1, p1)

Add a line segment, from [Point](Point.html) p1 to p2.

If the geometry already contains a [Curve](Curve.html) linking p1 and p2,
it is automatically added to this. If not, a new Curve
object is created.

Curves must be added *in order* , i.e. the start Point of
the current curve must equal the end Point of the
previously added Curve.

add_curve(this, geo.arc, p1, pcenter, p2)

Add a circle [Arc](Arc.html), from [Point](Point.html) p1 to p2, with its
center at [Point](Point.html) pcenter.

add_curve(this, Curve)

Add a [Curve](Curve.html) object to the boundary. _*TO BE
IMPLEMENTED*_

add_curve(this, geo.hole, surf1, surf2, ..)

Adds the surfaces surf1, surf2, .. as holes within this
surface.

**Note** : multiple calls to **add_curve** can be chained together
by simply passing all arguments to the method at once.
However, the *holes* , if any, must be supplied last and not
be followed by any Curves.

### * add_hole Add one or more holes to the surface.

add_hole(this, surface_1, ...)

### * area Return surface area(2D).

Calculate the **area** of this surface (polygon). See
this.points().

**NOTE** : after meshing the geometry, the **area** of the meshed
surface may not exactly equal the number returned by
area(this), especially if the surface contains [Arc](Arc.html)
boundaries.

### * fill Fill(-plot) surface

### * Surface.from_line is a function.
this = from_line(l, direction)

### * in_surface Point in surface?

bl = in_surface(this, X)

### * Surface/is_ccw is a function.
is_ccw = is_ccw(this)

### * plot Plot surface.

plot(this, args)

Plot surface with (args).

### * points Surface boundary as an array of doubles.

X = points(this)

Returns the x- and y-coordinates of the [Point](Point.html) objects
defining the boundary of this surface.

X = points(this, dense) use denser **points** for Arcs

### * reduce Reduce surface to the smallest possible area.

This method removes such holes (geo.hole) that share one or more boundary
Curves with this surface. For instance, a square surface with a smaller
square inside, tangenting on one edge, is reduced into a U-shaped
surface.

new_boundary_curves = reduce(this, [Point_start, Point_end] )

where Point_start and Point_end specify some boundary Line segment. The
method modifies the boundary of this surface accordingly, and
additionally returns the new boundary curves.

**NOTE**  The method works on *counterclockwise*  oriented surfaces, so the
start and end points must be selected accordingly.

WARNING : If Point_start and Point_end are joined by both a Line and one
or more Arcs, the Line is selected.

**NOTE**  This method must be called only after *all*  boundary-sharing holes
have been defined; the method cannot see the future.

### * reset_curves Remove all lines.

### * rotate_inplace Rotate surface in-place.

rotate_inplace(this, a) rotates all Points in this around the
Origin by the angle a.

