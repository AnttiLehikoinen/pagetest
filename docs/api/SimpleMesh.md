---
title : SimpleMesh
parent: API
grand_parent : Documentation
---
## Summary
SimpleMesh Basic mesh class.
## PROPERTIES
* SimpleMesh/element_type is a property.

* SimpleMesh/p is a property.

* SimpleMesh/t is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SimpleMesh/Bquiver is a function.
[Bvec, h] = Bquiver(this, A, els, varargin)

### * SimpleMesh Basic mesh class.

### * SimpleMesh/elementCenters is a function.
x0 = elementCenters(this, inds)

### * msh_getMappingMatrix mapping matrix from reference to global element.

Call syntax
[F, F0] = msh_getMappingMatrix(msh, elements) for an affine mapping
x_global = F:x_local + F0

OR

[dF/dx_local, F] = msh_getMappingMatrix(msh, elements, x_local) for
isoparametric mappings:
x_global = F

(c) 2018 Antti Lehikoinen / Aalto University

### * plot_edges Visualize edges

plot_edges(this, edge_indices)

plot_edges(this, edge_definitions)

plot_edges(this, inds, [plot_args](plot_args.html))

### * plot_nodes Plot nodes.

plot_nodes(this, node_indices, varargin)

Plot the nodes 'node_indices' with *varargin*  passed to
plot.

### * SimpleMesh/point2element is a function.
elements = point2element(this, X)

### * triplot Plot elements

triplot(this, element_indices, varargin)

Use element_indices = [] to plot all.

