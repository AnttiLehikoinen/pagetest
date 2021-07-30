---
title : Nedelec3DPrism
parent: API
grand_parent : Documentation
---
## Summary
Nedelec3D class for 3D Nedelec shape functions.

Only supports tets, so far.

(c) 2018 Antti Lehikoinen / Aalto University
## PROPERTIES
* Nedelec3DPrism/op is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nedelec3D class for 3D Nedelec shape functions.

Only supports tets, so far.

(c) 2018 Antti Lehikoinen / Aalto University

### * eval Evaluate global shape function.

Call syntax
w = this.eval(k, xref, msh, elements) or
w = this.eval(k, xref, msh, F, detF, elements)

### * eval Evaluate global shape function.

Call syntax
w = this.eval(k, xref, msh, elements) or
w = this.eval(k, xref, msh, F, detF, elements)

### * eval_ref Evaluate in reference element.

Call syntax
wref = this.eval_ref(k, xref, ~), where
k = number of edge, in [1,6]
xref = coordinate in reference tetrahedron.

Refence: "Higher Order Interpolatory Vector Bases on Prism
Elements"

### * getData get shape function and element data.

Call syntax
[Nf, order, Nvars] = this.getData(msh), where
Nf = number of shape functions per reference element
order = order of shape functions
Nvars = number of dofs in entire mesh.

### * getIndices Get indices of DoFs.

Call syntax
inds = this.getIndices(k, msh)
inds = this.getIndices(k, msh, elements), where
k = number of reference shape function.

