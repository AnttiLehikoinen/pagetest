---
title : MTPAinterpolant
parent: API
grand_parent : Documentation
---
## Summary
MTPAinterpolant Interpolant for post-processing field-weakening
behaviour
## PROPERTIES
* MTPAinterpolant/AC_loss_interpolant is a property.

* MTPAinterpolant/BEMF_grid is a property.

* MTPAinterpolant/DC_loss_interpolant is a property.

* MTPAinterpolant/I_MTPA is a property.

* MTPAinterpolant/RI_grid is a property.

* MTPAinterpolant/T_MTPA is a property.

* MTPAinterpolant/T_cutoff is a property.

* MTPAinterpolant/T_max is a property.

* MTPAinterpolant/UN is a property.

* MTPAinterpolant/XI_grid is a property.

* MTPAinterpolant/base_of_pu_speed is a property.

* MTPAinterpolant/data is a property.

* MTPAinterpolant/eddy_loss_interpolant is a property.

* MTPAinterpolant/hysteresis_loss_interpolant is a property.

* ready-made grids

* MTPAinterpolant/iq_grid is a property.

* MTPAinterpolant/n_cutoff is a property.

* MTPAinterpolant/torque_grid is a property.

* interpolants

## Methods
Class methods are listed below. Inherited methods are not included.
### * compute Compute operating-point behaviour

[Ptot, idq, E] = compute(this, T, n)

### * MTPAinterpolant/findI is a function.
i = findI(~, Ttarget, Icontour, Tcontour)

### * MTPAinterpolant/findT is a function.
t = findT(this, Tlevels, E)

### * MTPAinterpolant.from_grid is a function.
this = from_grid(grid, varargin)

### * MTPAinterpolant/init is a function.
init(this, Tn, nn, nrange, varargin)

### * initializing ready-made grids

### * torque interpolant

### * MTPAinterpolant/losses is a function.
[P, p_dc, p_hyst, p_eddy] = losses(this, id, iq, n)

### * MTPAinterpolant/rated_voltage_contour_at_speed is a function.
c = rated_voltage_contour_at_speed(this, n)

### * MTPAinterpolant/voltage is a function.
E = voltage(this, id, iq, n)

### * MTPAinterpolant/voltage_grid_at_speed is a function.
Ugrid = voltage_grid_at_speed(this, n)

