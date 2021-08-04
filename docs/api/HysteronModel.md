---
title : HysteronModel
parent: API
grand_parent : Documentation
---
## Summary
HysteronModel Base class for vector hysteron models

this = HysteronModel(Bs, M)

Piecewise linear shape functions are used. Hysteron evaluation
methods must be subclassed.

The model is stateful (p, B); re-initialization is triggered whenever
k_step_input < this.step in this.evaluate_H.
## PROPERTIES
* B_cand - current B-values

* B_previous - previous B-values

* B_saturation - saturation flux density

* M - number of hysterons

* dp - spacing between shape-function nodes

* ksis - hysteron limits

* p_cand - current hysteron values, possibly temporary

* p_previous - previous hysteron values

* shape_function_nodes - shape function interpolant x-data

* shape_function_values - shape function interpolant y-data

* step - current step

## Methods
Class methods are listed below. Inherited methods are not included.
### * HysteronModel Base class for vector hysteron models

this = HysteronModel(Bs, M)

Piecewise linear shape functions are used. Hysteron evaluation
methods must be subclassed.

The model is stateful (p, B); re-initialization is triggered whenever
k_step_input < this.step in this.evaluate_H.

### * HysteronModel/PlayModel is a function.
this = PlayModel(Bs, M)

### * HysteronModel/clear_copy is a function.
model = clear_copy(this)

### * eval_nodefun Evaluate one "shape function of shape function"

f = eval_nodefun(this, b, k, m)

Evaluates a piecewise-linear function with the input
argument b. This function has the value of 1 at
b = this.nodes(m)(k), and 0 at all other nodes.

### * evaluate_H Evaluate H-vector.

H = evaluate_H(this, Bin, kstep)

Evaluates H with the given B, at the given time-step, and updates the
state of this.

H = evaluate_H(this, Bin, false)

The same as above, but skip state-update.

### * evaluate_H_scalar Evaluate scalar model.

H = evaluate_H_scalar(this, Bin)

Evaluates scalar H with the input scalar time-series Bin.

### * evaluate_differential_reluctivity Evaluate differential reluctivity.

dHdB = evaluate_differential_reluctivity(this, Bin, kstep)

Evaluates the differential reluctivity dH/dB using numerical
differentiation.

### * evaluate_shape_function Evaluates the scalar shape functions.

Hout = evaluate_shape_function(this, pnorm, m)

### * evaluate_vector_hysteron Evaluate vector hysteron value.

Pout = evaluate_vector_hysteron(this, B, m)

Evaluates the hysteron m with the given input flux density (2xN
vector) and the current hysteron state, AND update the current
hysteron states.

Pout = evaluate_vector_hysteron(this, B, m, false)

The same as above, but don't update current state.

### * fit_model_with_least_squares Fit given model using non-negative
least-squares.

model = fit_model_with_least_squares(model, loops) fits the given model
to measured BH loops.

* model : a HysteronModel

* loops : an array of structs with the fields .B and .H

IMPORTANT: the given loop data should span one entire major BH loop, not
more and not less.

Fitting is is performed by feeding the given B-data to the model, and
fitting its output to the measured H, using monotonic non-negative
least-squares fitting on the shape function nodal values.

### * initialize Initializes the model.

initialize(this, Binit) initializes the model to the given initial flux
density vectors, using linear ramping.

### * ndof Number of free nodes in shape function.

n = ndof(this, m)

### * nodes Nodes of shape function.

bs = nodes(this, m)

### * sample_scalar_hysteron Evaluate scalar hysteron for series input.

bout = sample_scalar_hysteron(this, Bin, m) evaluates the m:th
scalar hysteron for the input time-series Bin.

### * set_new_step Increment step.

set_new_step(this, kstep) sets the current candidate state (p_cand,
B_cand) as the previous state (p_previous, B_previous)

### * set_shape_function_data Set shape function nodes from fitted vector.

set_shape_function_data(this, coeffs)

set_shape_function_data(this, cs, plot_results)

### * simulate_measured_loop Simulate H-values.

H = simulate_measured_loop(this, Bmeas)

Bmeas should consist of exactly one period of B.

