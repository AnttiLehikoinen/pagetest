---
title : SMGridCalculator_NTfromDQ
parent: API
grand_parent : Documentation
---
## Summary
SMGridCalculator_NTfromDQ methods:
SMGridCalculator_NTfromDQ - is a class.
compute_all - SMGridCalculator_NTfromDQ/compute_all is a function.
compute_point - SMGridCalculator_NTfromDQ/compute_point is a function.
get_results - Return an NTGrid object.
save_results_grid - SMGridCalculator_NTfromDQ/save_results_grid is a function.
setup_all - TODO needs better distribution of points for calculation
setup_point - SMGridCalculator_NTfromDQ/setup_point is a function.
## PROPERTIES
* SMGridCalculator_NTfromDQ/UDC is a property.

* SMGridCalculator_NTfromDQ/dqgrid is a property.

* SMGridCalculator_NTfromDQ/fs is a property.

* SMGridCalculator_NTfromDQ/interpolant is a property.

* SMGridCalculator_NTfromDQ/mode is a property.

* SMGridCalculator_NTfromDQ/supply_mode is a property.

* SMGridCalculator_NTfromDQ/waveform is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SMGridCalculator_NTfromDQ/SMGridCalculator_NTfromDQ is a constructor.
this = SMGridCalculator_NTfromDQ(dq_grid, motor, varargin)

### * SMGridCalculator_NTfromDQ/compute_all is a function.
this = compute_all(this)

### * SMGridCalculator_NTfromDQ/compute_point is a function.
solution = compute_point(this, ~)

### * get_results Return an NTGrid object.

results = get_results(this)

### * SMGridCalculator_NTfromDQ/save_results_grid is a function.
save_results_grid(this, fname, varargin)

### * TODO needs better distribution of points for calculation

### * SMGridCalculator_NTfromDQ/setup_point is a function.
this = setup_point(this, k)

