---
title : ExtrudedPrismMesh
parent: API
grand_parent : Documentation
---
## Summary
ExtrudedMachineMesh A base class for a MachineMesh extruded into 3D.

(c) 2017 Antti Lehikoinen / Aalto University
## PROPERTIES
* ExtrudedPrismMesh/Ne2 is a property.

* ExtrudedPrismMesh/Nfaces_square is a property.

* ExtrudedPrismMesh/Nfaces_tri is a property.

* ExtrudedPrismMesh/Nl is a property.

* ExtrudedPrismMesh/Np2 is a property.

* ExtrudedPrismMesh/faces_square is a property.

* ExtrudedPrismMesh/faces_tri is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * ExtrudedPrismMesh/Bquiver is a function.
[Bvec, h] = Bquiver(msh3, A, els, varargin)

### * extrudedMachineMesh constructor.

Call syntax
msh3 = extrudedMachineMesh(msh2) to extrude a MachineMesh and
generate a new ExtrudedMachineMesh object msh3.

### * ExtrudedPrismMesh/elementCenters is a function.
x0 = elementCenters(msh3, elem)

### * ExtrudedPrismMesh/extrudeElements is a function.
els = extrudeElements(msh3, els, varargin)

### * extrude_nodes

els = extrude_nodes(msh3, nodes)

els = extrude_nodes(msh3, nodes, layers)

### * ExtrudedPrismMesh/getMappingMatrix is a function.
[F, varargout] = getMappingMatrix(this, elem, varargin)

### * ExtrudedPrismMesh/grad_quiver is a function.
[Bvec, h] = grad_quiver(msh3, A, els, varargin)

### * ExtrudedPrismMesh/t is a function.
y = t(msh3)

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

