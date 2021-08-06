---
title : StopModel
parent: API
grand_parent : Documentation
---
## Summary
StopModel Hysteresis model based on Stop hysteron.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * StopModel Hysteresis model based on Stop hysteron.

### * evaluate_vector_hysteron Evaluate vector hysteron value.

Pout = evaluate_vector_hysteron(this, B, m)

Evaluates the hysteron m with the given input flux density (2xN
vector) and the current hysteron state, AND update the current
hysteron states.

Pout = evaluate_vector_hysteron(this, B, m, false)

The same as above, but don't update current state.
Help for StopModel/evaluate_vector_hysteron is inherited from superclass HYSTERONMODEL

### * from_least_squares_fit Initialize model from measured data.

this = from_least_squares_fit(M, loops) initialize a model of M
hysterons.

See HysteronModel.fit_model_with_least_squares

### * sample_scalar_hysteron Evaluate scalar hysteron for series input.

bout = sample_scalar_hysteron(this, Bin, m) evaluates the m:th
scalar hysteron for the input time-series Bin.
Help for StopModel/sample_scalar_hysteron is inherited from superclass HYSTERONMODEL

