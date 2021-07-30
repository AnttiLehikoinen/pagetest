---
title : OctTree
parent: API
grand_parent : Documentation
---
## Summary
OctTree methods:
OctTree - is a class.
from_mesh - OctTree.from_mesh is a function.
from_parent - OctTree.from_parent is a function.
## PROPERTIES
* OctTree/MAX_DEPTH is a property.

* OctTree/MIN_ELEMENTS is a property.

* OctTree/c_lll is a property.

* OctTree/c_lls is a property.

* OctTree/c_lsl is a property.

* OctTree/c_lss is a property.

* OctTree/c_sll is a property.

* OctTree/c_sls is a property.

* OctTree/c_ssl is a property.

* OctTree/c_sss is a property.

* child nodes

* OctTree/depth is a property.

* OctTree/elements is a property.

* mesh limits

* OctTree/mxmax is a property.

* OctTree/mxmin is a property.

* OctTree/mymax is a property.

* OctTree/mymin is a property.

* OctTree/mzmax is a property.

* OctTree/mzmin is a property.

* OctTree/parent is a property.

* OctTree/xmax is a property.

* OctTree/xmin is a property.

* OctTree/ymax is a property.

* OctTree/ymin is a property.

* OctTree/zmax is a property.

* OctTree/zmin is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * COUNT Returns the number of occurrences of a pattern in text.
C = COUNT(STR,PATTERN) returns the number of occurrences of PATTERN in
STR.

STR can be a string array, a character vector, or a cell array of
character vectors. So can PATTERN. PATTERN and STR need not be the same
size. If PATTERN is a string array or a cell array, then COUNT returns
the total number of occurrences of all elements of PATTERN in STR.

C = COUNT(STR,PATTERN,'IgnoreCase',IGNORE) ignores case when searching
for PATTERN in STR if IGNORE is true. The default value of IGNORE is false.

Examples
STR = "data.tar.gz";
P = "tar";
COUNT(STR,P)                   returns  1

STR = ["abstracts.docx","data.tar.gz"];
P = 'tar';
COUNT(STR,P)                   returns  [0 1]

STR = "data.tar.gz";
P = {'docx','tar'};
COUNT(STR,P)                   returns  1

STR = {'DATA.TAR.GZ','SUMMARY.PPT'};
P = "tar";
COUNT(STR,P,'IgnoreCase',true) returns  [1 0]

See also endsWith, startsWith, contains.

### * find Find OctTreeNode containing given point.

### * OctTree/find_closest_local is a function.
[x_local, elements] = find_closest_local(this, X)

### * OctTree.from_mesh is a function.
this = from_mesh(m3d, varargin)

### * OctTree.from_parent is a function.
this = from_parent(parent, elements, xmin, xmax, ymin, ymax, zmin, zmax)

### * OctTree/get_root is a function.
p = get_root(this)

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

### * center points

