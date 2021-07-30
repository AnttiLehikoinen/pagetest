---
title : Elements
parent: API
grand_parent : Documentation
---
## Summary
{
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * {

### * Elements.composite is a function.
e = composite

### * Elements.isIsoparametric is a function.
bl = isIsoparametric(type)

### * Elements.isPrism is a function.
bl = isPrism(type)

### * Elements.isTet is a function.
bl = isTet(type)

### * Elements.isTriangle is a function.
bl = isTriangle(type)

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

### * PRISM  Prism color map
PRISM(M) returns an M-by-3 matrix containing repeated use
of six colors: red, orange, yellow, green, blue, violet.
PRISM, by itself, is the same length as the current figure's
colormap. If no figure exists, MATLAB creates one.

PRISM, with no input or output arguments, changes the colors
of any line objects in the current axes to the **prism** colors.

The colors in the PRISM map are also present, in the same order,
in the HSV map.  However, PRISM uses repeated copies of its six
colors, whereas HSV varies its colors smoothly.

See also HSV, FLAG, HOT, COOL, COLORMAP, RGBPLOT, CONTOUR.

### * QUAD   Numerically evaluate integral, adaptive Simpson quadrature.
Q = QUAD(FUN,A,B) tries to approximate the integral of scalar-valued
function FUN from A to B to within an error of 1.e-6 using recursive
adaptive Simpson quadrature. FUN is a function handle. The function
Y=FUN(X) should accept a vector argument X and return a vector result
Y, the integrand evaluated at each element of X.

Q = QUAD(FUN,A,B,TOL) uses an absolute error tolerance of TOL
instead of the default, which is 1.e-6.  Larger values of TOL
result in fewer function evaluations and faster computation,
but less accurate results.  The QUAD function in MATLAB 5.3 used
a less reliable algorithm and a default tolerance of 1.e-3.

Q = QUAD(FUN,A,B,TOL,TRACE) with non-zero TRACE shows the values
of [fcnt a b-a Q] during the recursion. Use [] as a placeholder to
obtain the default value of TOL.

[Q,FCNT] = QUAD(...) returns the number of function evaluations.

Use array operators .*, ./ and .^ in the definition of FUN
so that it can be evaluated with a vector argument.

QUAD will be removed in a future release. Use INTEGRAL instead.

Example:
Q = quad(@myfun,0,2);
where the file myfun.m defines the function:
%-------------------%
function y = myfun(x)
y = 1./(x.^3-2*x-5);
%-------------------%

or, use a parameter for the constant:
Q = quad(@(x)myfun2(x,5),0,2);
where the file myfun2.m defines the function:
%----------------------%
function y = myfun2(x,c)
y = 1./(x.^3-2*x-c);
%----------------------%

Class support for inputs A, B, and the output of FUN:
float: double, single

See also INTEGRAL, INTEGRAL2, INTEGRAL3, QUADGK, QUAD2D, TRAPZ,
FUNCTION_HANDLE.

### * Elements.refPoints_edges is a function.
X = refPoints_edges(type, varargin)

### * Elements.refPoints_nodes is a function.
X = refPoints_nodes(type)

### * Elements.tet is a function.
e = tet

### * Elements.triangle is a function.
e = triangle

### * Elements.triangle2 is a function.
e = triangle2

### * Elements.triangle2I is a function.
e = triangle2I

