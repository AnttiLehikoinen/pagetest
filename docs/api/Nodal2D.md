---
title : Nodal2D
parent: API
grand_parent : Documentation
---
## Summary
Nodal2D Lagrange (nodal) shape function in 2D.

Class for representing and evaluating shape functions and their partial derivatives.
Objects of the class can be instantiated with

* N = Nodal2D( Operators.I ) or Nodal2D() for evaluating the function
itself.

* N = Nodal2D( Operators.grad ) for evaluating function gradients.

* N = Nodal2D( Operators.curl ) for evaluating curls.

The actual evaluation is performed with N.eval(args) by
specifying

* the mesh used

* elements of the mesh to evaluate on

* LOCAL coordinates to evaluate on. The local coordinates must fall
within the so-called reference element (unit-triangle ((0,0),
(1,0), (0,1)) for triangular elements) associated with the mesh
element types. The actual evaluation then takes place on the GLOBAL
coordinates, i.e. a point within each of the listed *elements*
corresponding to the given local coordinate. For instance, the
local point [0.25;0.25] is mapped (more or less) to the global element
center.

* Index of shape function. As nodal shape functions are each
associated with a mesh node, there are 3 shape functions that are
non-zero over a first-order element. Example: for the element *e* ,
the shape function *k*  is associated the node mesh.t(k, e).
## PROPERTIES
* op - operator

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nodal2D Constructor

this = Nodal()

For evaluating raw nodal shape function N.

this = Nodal( Operators.grad )

this = Nodal( Operators.curl )

For evaluating grad N or curl N, respectively.

### * eval Global evaluation.

vals = eval(this, k, x_local, mesh, elements)

Evaluates (this.op x N_k), where N_k is the k:th node of
the elementType of the given mesh. The expression is
evaluated at the *global*  coordinates
corresponding to the given *local*  coordinates, on the
specified *elements*  of the given *mesh* .

Input arguments:

* k : index of shape function to evaluate. 1...3 for
first-order triangular elements.

* x_local : local coordinates to evaluate at.

* mesh : the mesh to evaluate on.

* elements : indices of elements (mesh.t(:, elements))
to evaluate on.


vals = eval(this, k, x_local, mapping, mapping_determinant)

The same as above, but specify the local-to-global mapping
and its determinant instead of the element indices. Mainly
used for speed purposes.

Input arguments:

* mapping : see SimpleMesh.getMappingMatrix

* mapping_determinant : see MatrixDeterminant

### * evaluates the reference shape function (either identity or
gradient)

Nref = eval(ref, this, k, x_local, mesh)

### * getData Data for matrix assembly.

### * Nodal2D/getIndices is a function.
inds = getIndices(~, k, msh, varargin)

