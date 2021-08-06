---
title : eSurface
parent: API
grand_parent : Documentation
---
## Summary
eSurface methods:
add_curve - eSurface/add_curve is a function.
create - Get existing surface or create new.
eSurface - is a class.
flatten - getting points
get_all_points - eSurface/get_all_points is a function.
periodic_pair - eSurface/periodic_pair is a function.
raise_axially - eSurface/raise_axially is a function.
raise_axially_curves_and_surfaces - eSurface/raise_axially_curves_and_surfaces is a function.
raise_radially - getting all points
raise_radially_along_sector - getting all points
raise_radially_curves_and_surfaces - eSurface/raise_radially_curves_and_surfaces is a function.
set_characteristic_length - eSurface/set_characteristic_length is a function.
## PROPERTIES
* eSurface/bottom_volume is a property.

* eSurface/curve_directions is a property.

* eSurface/curves is a property.

* eSurface/is_closed is a property.

* eSurface/is_flat is a property.

* eSurface/periodic_with is a property.

* eSurface/sector_angle is a property.

* eSurface/top_volume is a property.

* eSurface/type is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * eSurface/add_curve is a function.
add_curve(this, curve)

### * eSurface/center_of_mass is a function.
x = center_of_mass(this)

### * eSurface/close_surface is an undocumented builtin eSurface method.

### * create Get existing surface or **create** new.

### * eSurface/eSurface is a constructor.
this = eSurface

### * getting points

### * eSurface/get_all_points is a function.
ps = get_all_points(this)

### * eSurface/normal is a function.
n = normal(this)

### * eSurface/periodic_pair is a function.
sout = periodic_pair(this)

### * PLOT   Linear plot.
PLOT(X,Y) plots vector Y versus vector X. If X or Y is a matrix,
then the vector is plotted versus the rows or columns of the matrix,
whichever line up.  If X is a scalar and Y is a vector, disconnected
line objects are created and plotted as discrete points vertically at
X.

PLOT(Y) plots the columns of Y versus their index.
If Y is complex, PLOT(Y) is equivalent to PLOT(real(Y),imag(Y)).
In all other uses of PLOT, the imaginary part is ignored.

Various line types, **plot** symbols and colors may be obtained with
PLOT(X,Y,S) where S is a character string made from one element
from any or all the following 3 columns:

b     blue          .     point              -     solid
g     green         o     circle             :     dotted
r     red           x     x-mark             -.    dashdot
c     cyan          +     plus               --    dashed
m     magenta       *     star             (none)  no line
y     yellow        s     square
k     black         d     diamond
w     white         v     triangle (down)
^     triangle (up)
<     triangle (left)
>     triangle (right)
p     pentagram
h     hexagram

For example, PLOT(X,Y,'c+:') plots a cyan dotted line with a plus
at each data point; PLOT(X,Y,'bd') plots blue diamond at each data
point but does not draw any line.

PLOT(X1,Y1,S1,X2,Y2,S2,X3,Y3,S3,...) combines the plots defined by
the (X,Y,S) triples, where the X's and Y's are vectors or matrices
and the S's are strings.

For example, PLOT(X,Y,'y-',X,Y,'go') plots the data twice, with a
solid yellow line interpolating green circles at the data points.

The PLOT command, if no color is specified, makes automatic use of
the colors specified by the axes ColorOrder property.  By default,
PLOT cycles through the colors in the ColorOrder property.  For
monochrome systems, PLOT cycles over the axes LineStyleOrder property.

Note that RGB colors in the ColorOrder property may differ from
similarly-named colors in the (X,Y,S) triples.  For example, the
second axes ColorOrder property is medium green with RGB [0 .5 0],
while PLOT(X,Y,'g') plots a green line with RGB [0 1 0].

If you do not specify a marker type, PLOT uses no marker.
If you do not specify a line style, PLOT uses a solid line.

PLOT(AX,...) plots into the axes with handle AX.

PLOT returns a column vector of handles to lineseries objects, one
handle per plotted line.

The X,Y pairs, or X,Y,S triples, can be followed by
parameter/value pairs to specify additional properties
of the lines. For example, PLOT(X,Y,'LineWidth',2,'Color',[.6 0 0])
will create a **plot** with a dark red line width of 2 points.

Example
x = -pi:pi/10:pi;
y = tan(sin(x)) - sin(tan(x));
plot(x,y,'--rs','LineWidth',2,...
'MarkerEdgeColor','k',...
'MarkerFaceColor','g',...
'MarkerSize',10)

See also PLOTTOOLS, SEMILOGX, SEMILOGY, LOGLOG, PLOTYY, PLOT3, GRID,
TITLE, XLABEL, YLABEL, AXIS, AXES, HOLD, LEGEND, SUBPLOT, SCATTER.

### * eSurface/plot_normal is a function.
plot_normal(this, varargin)

### * eSurface/points is a function.
xs = points(this)

### * eSurface/raise_axially is a function.
V = raise_axially(this, level, varargin)

### * eSurface/raise_axially_curves_and_surfaces is a function.
V = raise_axially_curves_and_surfaces(this, level)

### * getting all points

### * getting all points

### * eSurface/set_characteristic_length is a function.
set_characteristic_length(this, lcar)

