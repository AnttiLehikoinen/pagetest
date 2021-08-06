---
title : NTGridNT
parent: API
grand_parent : Documentation
---
## Summary



FIXME rename P_Cu_DC to P_Cu_total
## PROPERTIES
* NTGridNT/Tgrid is a property.

* NTGridNT/data is a property.

* NTGridNT/interpolants is a property.

* NTGridNT/loss_grid is a property.

* NTGridNT/ngrid is a property.

* NTGridNT/voltage_grid is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * 


FIXME rename P_Cu_DC to P_Cu_total

### * NTGridNT/get_efficiency_grid is a function.
[etagrid, electrical_power] = get_efficiency_grid(this, varargin)

### * selecting desired interpolant

### * efficiency Evaluate efficiency at given points.

### * NTGridNT/plot_efficiency_grid is a function.
plot_efficiency_grid(this, varargin)

### * NTGridNT/plot_grid is a function.
grid = plot_grid(this, varname, varargin)

### * save_efficiency_grid Save efficiency data.

save_efficiency_grid(this, filename)

save_efficiency_grid(this, filename, key, val) with

* 'format', 'grid'/'columns' : Output format. Only 'columns' supported
right now.

* 'sheet', sheet_name : Sheet to save into.

* 'range', rng : Sheet range to save into. Default 'A1'.

### * setup_all Setup NTgrid.

this = setup_all(this, raw_grid)

