---
title : HysteresisModel
parent: API
grand_parent : Documentation
---
## Summary
HysteresisModel Base class for hysteresis models.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * HysteresisModel Base class for hysteresis models.

### * clear_copy Returns a new instance with default state.

### * evaluate_H Evaluate H for given input.

H = evaluate_H(this, B, step), where

* B : ndim x N vector

* step : number of time-step

H = evaluate_H(this, B, step, varargin)

### * evaluate_differential_reluctivity Evaluate differential
reluctivity.

The same as evaluate_H, but returns the differential reluctivity
tensor dH/dB instead.

