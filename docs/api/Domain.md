---
title : Domain
parent: API
grand_parent : Documentation
---
## Summary
Domain Domain class.

In `EMDtool` , a 'Domain' represents all aspects of some interesting part of an
electric machine or electromagnetic problem. Thus, a domain has

* A [Material](Material.html) that it consists of

* One or more <Surface.html Surfaces>

Instantiation:

this = Domain(domain_name, material_object)

this = Domain(domain_name, material_object, surface_1, surface_2,
...)

Surfaces can be added with `this.add_surface`
## PROPERTIES
* copied_from - a Domain that his has been replicated from, if any

* copied_to - a Domain that this has been replicated to, if any

* elements - Indices of the elements, in this.root().mesh

* material - The [Material](Material.html) that this domain consists of

* orientation - **orientation** (for e.g. anisotropic materials

* remanence_direction - remanence flux density direction, if any

* surfaces - 2D **surfaces** in this

* volumes - 3D volumes, if any (experimental)

## Methods
Class methods are listed below. Inherited methods are not included.
### * Domain **Domain** class.

In `EMDtool` , a 'Domain' represents all aspects of some interesting part of an
electric machine or electromagnetic problem. Thus, a domain has

* A [Material](Material.html) that it consists of

* One or more <Surface.html Surfaces>

Instantiation:

this = Domain(domain_name, material_object)

this = Domain(domain_name, material_object, surface_1, surface_2,
...)

Surfaces can be added with `this.add_surface`

### * add_surface Add one or more Surfaces to this.

### * add_volume Add one or more volumes to this.

### * AREA  Filled **area** 2-D plot.
AREA(Y) plots the vector Y or plots each column in matrix Y as a
separate curve and stacks the curves. The x-axis automatically
scales to 1:size(Y,1). The values in Y can be numeric or duration
values.

AREA(X,Y) plots Y versus X and fills the **area** between 0 and Y. The
values in X can be numeric, datetime, duration or categorical
values.

If Y is a vector, then specify X as a vector of increasing
values with length equal to Y. If the values in X are not
increasing, then AREA sorts the values before plotting.

If Y is a matrix, then specify X as a vector of increasing
values with length equal to the number of rows in Y. AREA plots
the columns of Y as filled areas. For each X, the net result is
the sum of corresponding values from the rows of Y. You also
can specify X as a matrix with size equal to Y. To avoid
unexpected output when X is a matrix, specify X so that the
columns repeat.

AREA( ** _ ,BASEVALUE) specifies the base value for the **area** fill.
The default BASEVALUE is 0. Specify the base value as a numeric
value.

AREA( ** _ ,Name,Value) modifies the appearance of the **area** chart
using one or more name-value pair arguments.

AREA(AX, ** _ ) plots into the axes specified by AX instead of the
current axes.

H = AREA( ** _ ) returns one or more Area objects. AREA creates one
object for vector input arguments and one object per column for
matrix input arguments.

See also PLOT, BAR.

### * parsing center

### * copy Deep **copy** of this.

### * copy_root Original ancestor in replication chain

### * last_copy Latest domain in replication chain

### * Domain/mass is a function.
m = mass(this)

### * plot Plot all surfaces in 2D.

### * plot3 Plot all surfaces in 3D.

### * plot_remanence_direction Plot remanence.

plot_remanence_direction(this, varargin) plots remanence
direction using quiver, with varargin.

### * remanence_direction Remanence direction vector.

### * Domain/visualize is a function.
visualize(this, varargin)

