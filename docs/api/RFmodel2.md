---
title : RFmodel2
parent: API
grand_parent : Documentation
---
## Summary
RFmodel2 methods:
RFmodel2 - is a class.
add_component - Add component to RFmodel2
finalize - finalizing mesh part
get_AGmatrix - RFmodel2/get_AGmatrix is a function.
mass - RFmodel2/mass is a function.
visualize - Visualize geometry.
## PROPERTIES
* RFmodel2/Ne_component is a property.

* RFmodel2/Np_component is a property.

* RFmodel2/airgap is a property.

* RFmodel2/circuits is a property.

* RFmodel2/components is a property.

* RFmodel2/periodicityCoeff is a property.

* RFmodel2/ri_component is a property.

* RFmodel2/rotor is a property.

* RFmodel2/stator is a property.

* RFmodel2/symmetrySectors is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * RFmodel2/RFmodel2 is a constructor.
this = RFmodel2(dim)

### * add_component Add component to RFmodel2

### * RFmodel2/add_gap is a function.
add_gap(this, static_part, moving_part)

### * RFmodel2/compute_torque is a function.
T = compute_torque(this, solution)

### * finalizing mesh part

### * RFmodel2/get_AGmatrix is a function.
S = get_AGmatrix(this, rotorAngle, varargin)

### * RFmodel2/global_element_indices is a function.
is = global_element_indices(this, is, component)

### * RFmodel2/global_node_indices is a function.
ns = global_node_indices(this, ns, component)

### * RFmodel2/mass is a function.
[m, m_domain, m_mat] = mass(this)

### * RFmodel2/plot_flux is a function.
plot_flux(~, solution, step)

### * RFmodel2/rotel is a function.
els = rotel(this)

### * RFmodel2/set_outer_boundary is a function.
set_outer_boundary(this, varargin)

### * VISUALIZE Visualize geometry.

