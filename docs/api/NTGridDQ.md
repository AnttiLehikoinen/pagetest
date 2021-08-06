---
title : NTGridDQ
parent: API
grand_parent : Documentation
---
## Summary
NTGridDQ Speed-torque grid from d-q grid data.

Initialization:

grid = NTGridDQ(raw_grid, key, val) with any of the following:

* 'U_DC' : DC-link voltage. Default [] --> determine from base
point.

* 'turns_ratio' : multiplier to adjust the motor turn count with.

* 'base_speed' : Base speed, see below.

* 'base_torque' : Base torque. Not used if U_DC is given. If not,
then U_DC = terminal voltage at base point.

* 'speed_range' : speed range to initialize the grid for.
## PROPERTIES
* U_DC - DC bus voltage. Changing this recomputes this.interpolant

* base_speed - Base speed

* base_torque - Base torque

* NTGridDQ/grid is a property.

* NTGridDQ/interpolant is a property.

* NTGridDQ/speed_range is a property.

* turns_ratio - Multiplier for motor turns. Changing this recomputes this.interpolant.

## Methods
Class methods are listed below. Inherited methods are not included.
### * parsing defaults

### * NTGridDQ/get_efficiency_grid is a function.
[etagrid, torque_grid, speed_grid, electrical_power] = get_efficiency_grid(this, varargin)

### * NTGridDQ/get_grid is a function.
[Qint, torque_grid, speed_grid] = get_grid(this, q_name, varargin)

### * NTGridDQ/get_op is a function.
[eta, I, Pcu, Physt, Peddy] = get_op(this, n, T, varargin)

### * get_speed_and_torque_grid Meshgrids for calculation.

### * init_listeners Add property listeners.

### * NTGridDQ/plot_map is a function.
Qint = plot_map(this, contour_name, varargin)

### * setting up grids

### * setup Initialization function

### * save_efficiency_grid Save efficiency data.

save_efficiency_grid(this, filename)

save_efficiency_grid(this, filename, key, val) with

* 'format', 'grid'/'columns' : Output format. Only 'columns' supported
right now.

* 'sheet', sheet_name : Sheet to save into.

* 'range', rng : Sheet range to save into. Default 'A1'.

