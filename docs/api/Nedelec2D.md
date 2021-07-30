---
title : Nedelec2D
parent: API
grand_parent : Documentation
---
## Summary
Nedelec2D class for 2D Nedelec shape functions.
## PROPERTIES
* Nedelec2D/op is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Nedelec2D class for 2D Nedelec shape functions.

### * eval Evaluate global shape function.

Call syntax
w = this.eval(k, xref, msh, elements) or
w = this.eval(k, xref, msh, F, detF, elements)

### * eval_ref Evaluate in reference element.

Call syntax
wref = this.eval_ref(k, xref, ~), where
k = number of edge, in [1,3]
xref = coordinate in reference element.

Refence: "Fast MATLAB assembly of FEM matrices in 2D and 3D:
Edge elements"

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

