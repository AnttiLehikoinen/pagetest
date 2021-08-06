---
title : PlayModel
parent: API
grand_parent : Documentation
---
## Summary
PlayModel Play hysteron model.

Currently probably not up-to-date.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * PlayModel Play hysteron model.

Currently probably not up-to-date.

### * evaluate_H Evaluate H-vector.

H = evaluate_H(this, Bin, kstep)

Evaluates H with the given B, at the given time-step, and updates the
state of this.

H = evaluate_H(this, Bin, false)

The same as above, but skip state-update.
Help for PlayModel/evaluate_H is inherited from superclass HYSTERONMODEL

### * evaluate_differential_reluctivity Evaluate differential reluctivity.

dHdB = evaluate_differential_reluctivity(this, Bin, kstep)

Evaluates the differential reluctivity dH/dB using numerical
differentiation.
Help for PlayModel/evaluate_differential_reluctivity is inherited from superclass HYSTERONMODEL

### * PlayModel/evaluate_scalar_hysteron is a function.
p = evaluate_scalar_hysteron(this, B, p0, m)

### * evaluate_shape_function Evaluates the scalar shape functions.

Hout = evaluate_shape_function(this, pnorm, m)
Help for PlayModel/evaluate_shape_function is inherited from superclass HYSTERONMODEL

### * evaluate_vector_hysteron Evaluate vector hysteron value.

Pout = evaluate_vector_hysteron(this, B, m)

Evaluates the hysteron m with the given input flux density (2xN
vector) and the current hysteron state, AND update the current
hysteron states.

Pout = evaluate_vector_hysteron(this, B, m, false)

The same as above, but don't update current state.
Help for PlayModel/evaluate_vector_hysteron is inherited from superclass HYSTERONMODEL

### * initialize Initializes the model.

initialize(this, Binit) initializes the model to the given initial flux
density vectors, using linear ramping.
Help for PlayModel/initialize is inherited from superclass HYSTERONMODEL

### * sample_scalar_hysteron Evaluate scalar hysteron for series input.

bout = sample_scalar_hysteron(this, Bin, m) evaluates the m:th
scalar hysteron for the input time-series Bin.
Help for PlayModel/sample_scalar_hysteron is inherited from superclass HYSTERONMODEL

### * set_new_step Increment step.

set_new_step(this, kstep) sets the current candidate state (p_cand,
B_cand) as the previous state (p_previous, B_previous)
Help for PlayModel/set_new_step is inherited from superclass HYSTERONMODEL

### * set_shape_function_data Set shape function nodes from fitted vector.

set_shape_function_data(this, coeffs)

set_shape_function_data(this, cs, plot_results)
Help for PlayModel/set_shape_function_data is inherited from superclass HYSTERONMODEL

