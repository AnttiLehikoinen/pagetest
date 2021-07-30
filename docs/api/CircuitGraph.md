---
title : CircuitGraph
parent: API
grand_parent : Documentation
---
## Summary
CircuitGraph methods:
CircuitGraph - is a class.
create_tree - CircuitGraph/create_tree is a function.
find_connection - CircuitGraph/find_connection is a function.
form_loops - CircuitGraph/form_loops is a function.
initialize - CircuitGraph/initialize is a function.
visualize_edges - CircuitGraph/visualize_edges is a function.
visualize_graph - CircuitGraph/visualize_graph is a function.
visualize_tree - CircuitGraph/visualize_tree is a function.
## PROPERTIES
* CircuitGraph/edge_weights is a property.

* CircuitGraph/edges is a property.

* CircuitGraph/node_coordinates is a property.

* CircuitGraph/nodes is a property.

* CircuitGraph/nodes2edges is a property.

* CircuitGraph/tree is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * CircuitGraph/CircuitGraph is a constructor.
this = CircuitGraph(edges, ew)

### * CircuitGraph/create_tree is a function.
create_tree(this)

### * CircuitGraph/find_connection is a function.
inds = find_connection(this, k)

### * CircuitGraph/form_loops is a function.
L = form_loops(this)

### * CircuitGraph/initialize is a function.
initialize(this)

### * CircuitGraph/visualize_edges is a function.
visualize_edges(this, inds, varargin)

### * CircuitGraph/visualize_graph is a function.
visualize_graph(this)

### * CircuitGraph/visualize_tree is a function.
visualize_tree(this)

