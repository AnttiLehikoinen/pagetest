---
title : SMGridCalculator_NT
parent: API
grand_parent : Documentation
---
## Summary
SMGridCalculator_NT (rpm, T) operating point grid calculator.
## PROPERTIES
* SMGridCalculator_NT/iterator is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SMGridCalculator_NT (rpm, T) operating point grid calculator.

### * SMGridCalculator_NT/compute_all is a function.
this = compute_all(this)

### * SMGridCalculator_NT/compute_point is a function.
[solution, target_reached] = compute_point(this, k)

### * get_results Return an NTGrid object.

results = get_results(this)

### * SMGridCalculator_NT/setup_all is a function.
this = setup_all(this, motor, varargin)

### * Does nothing.

