---
title : TetMesh
parent: API
grand_parent : Documentation
---
## Summary
TetMesh minimal mesh of 3D tetrahedrons.

(c) 2018 Antti Lehikoinen / Aalto University
## PROPERTIES
* TetMesh/data is a property.

* TetMesh/dirichlet_boundaries is a property.

* TetMesh/edges is a property.

* TetMesh/elementType is a property.

* TetMesh/elements is a property.

* TetMesh/elements2edges is a property.

* TetMesh/entities is a property.

* TetMesh/nodes is a property.

* TetMesh/p is a property.

* TetMesh/periodic_boundaries is a property.

* TetMesh/t is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * TetMesh/A is a function.
Bvec = A(this, A, els, varargin)

### * TetMesh/Aquiver is a function.
[Bvec, h] = Aquiver(this, A, els, varargin)

### * TetMesh/B is a function.
Bvec = B(this, A, els, varargin)

### * TetMesh/Bquiver is a function.
[Bvec, h] = Bquiver(this, A, els, varargin)

### * TetMesh/J is a function.
Bvec = J(this, N, els, varargin)

### * TetMesh/Nquiver is a function.
[Bvec, h] = Nquiver(this, N, els, varargin)

### * TetMesh mesh constructor.

Call syntax
msh = SimpleTetMesh(p, t)

### * TetMesh/closest_local is a function.
[x_closest, ind] = closest_local(this, X, els)

### * TetMesh/elementCenters is a function.
x0 = elementCenters(this, elem)

### * TetMesh/element_nodal_coordinates is a function.
ps = element_nodal_coordinates(this, k, els)

### * getMappingMatrix Mapping matrix from reference to global
element.

Call syntax
[F, F0] = getMappingMatrix(this, elem) OR
[F, F0] = getMappingMatrix(this, elem, unused_args)

### * init Initialize edge arrays and element-edge incidence.

### * TetMesh/integration_point is a function.
[x_quad, w_quad] = integration_point(this, order)

### * TetMesh/plot_edges is a function.
plot_edges(this, inds, varargin)

### * TetMesh/plot_nodes is a function.
plot_nodes(this, inds, varargin)

### * init Initialize edge arrays and element-edge incidence.

### * TetMesh/to_local is a function.
x = to_local(this, X, els)

### * TRIPLOT Plots a 2D triangulation
TRIPLOT(TRI,X,Y) displays the triangles defined in the
M-by-3 matrix TRI.  A row of TRI contains indices into X,Y that
define a single triangle. The default line color is blue.

TRIPLOT(TR) displays the triangles in the triangulation TR.

TRIPLOT(...,COLOR) uses the string COLOR as the line color.

H = TRIPLOT(...) returns a line handle representing the displayed
triangles edges.

TRIPLOT(...,'param','value','param','value'...) allows additional
line param/value pairs to be used when creating the plot.

Example 1:
X = rand(10,2);
dt = delaunayTriangulation(X);
triplot(dt)

Example 2:
% Plotting a Delaunay triangulation in face-vertex format
X = rand(10,2);
dt = delaunayTriangulation(X);
tri = dt(:,:);
triplot(tri, X(:,1), X(:,2));

See also TRISURF, TRIMESH, DELAUNAY, triangulation, delaunayTriangulation.

