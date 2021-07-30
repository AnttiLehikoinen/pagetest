---
title : Operators
parent: API
grand_parent : Documentation
---
## Summary
{
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * Operators.I is a function.
e = I

### * {

### * CURL  Curl and angular velocity of a vector field.
[CURLX, CURLY, CURLZ, CAV] = CURL(X,Y,Z,U,V,W) computes the
curl and angular velocity perpendicular to the flow (in radians
per time unit) of a 3D vector field U,V,W. The arrays X,Y,Z
define the coordinates for U,V,W and must be monotonic and 3D
plaid (as if produced by MESHGRID).

[CURLX, CURLY, CURLZ, CAV] = CURL(U,V,W) assumes
[X Y Z] = meshgrid(1:N, 1:M, 1:P) where [M,N,P]=SIZE(U).

[CURLZ, CAV]= CURL(X,Y,U,V) computes the **curl** z component and
angular velocity perpendicular to z (in radians per time unit)
of a 2D vector field U,V. The arrays X,Y define the
coordinates for U,V and must be monotonic and 2D plaid (as if
produced by MESHGRID).

[CURLZ, CAV] = CURL(U,V) assumes
[X Y] = meshgrid(1:N, 1:M) where [M,N]=SIZE(U).

[CURLX, CURLY, CURLZ] = CURL(...) or
[CURLX, CURLY] = CURL(...) returns only the curl.

CAV = CURL(...) returns only the **curl** angular velocity.

Example 1:
load wind
cav = curl(x,y,z,u,v,w);
slice(x,y,z,cav,[90 134],[59],[0]); shading interp
daspect([1 1 1])
camlight

Example 2:
load wind
k = 4;
x = x(:,:,k); y = y(:,:,k); u = u(:,:,k); v = v(:,:,k);
cav = curl(x,y,u,v);
pcolor(x,y,cav); shading interp
hold on; quiver(x,y,u,v)

See also STREAMRIBBON, DIVERGENCE.

### * Operators.div is a function.
e = div

### * Operators.grad is a function.
e = grad

