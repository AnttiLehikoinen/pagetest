---
title : FieldWindingSpec
parent: API
grand_parent : Documentation
---
## Summary
FieldWindingSpec methods:
FieldWindingSpec - is a class.
## PROPERTIES
* c - FIXME

* overhang_length - winding overhang length
Help for FieldWindingSpec/overhang_length is inherited from superclass POLYPHASEWINDINGSPEC

## Methods
Class methods are listed below. Inherited methods are not included.
### * FieldWindingSpec/FieldWindingSpec is a constructor.
this = FieldWindingSpec(varargin)

### * end_winding_loop_matrix End-winding loop matrix, slot-segment.

L = end_winding_loop_matrix(this)

Returns a number_of_slots x phases matrix, representing how many
times each phase traverses each 'slot segment' = end-winding
piece between two successive slots.

Only computed for one end of a radial-flux machine.
Help for FieldWindingSpec/end_winding_loop_matrix is inherited from superclass POLYPHASEWINDINGSPEC

### * end_winding_segment_inductance Inductance of one end-winding segment.

Calculation somewhat follows the approach given by Lipo, T.A. (*) for a random-wound
winding. Iron modelled as perfect conductor, to accound for eddy damping.

(*) Introduction to AC Machine Design

Only works for radial-flux machines.
Help for FieldWindingSpec/end_winding_segment_inductance is inherited from superclass POLYPHASEWINDINGSPEC

### * FieldWindingSpec/line_current_matrix is a function.
M = line_current_matrix(this)

### * FieldWindingSpec/line_to_line_voltage_matrix is a function.
M = line_to_line_voltage_matrix(this)

### * set_layout_matrix Initialize winding layout matrix.

A layout matrix is a number_of_layers x number_of_slots matrix of
integers, with values in range -phases...phases.

The entries of the layout matrix W are:

*  W(i, j) = +k : phase k goes through layer i, slot j, to
positive direction:

* W(i, j) = -k : phase k goes through layer i, slot j, to
negative direction:
Help for FieldWindingSpec/set_layout_matrix is inherited from superclass POLYPHASEWINDINGSPEC

### * winding_angle Compute winding angle.

a = winding_angle(this)

Compute the stator *winding angle*  i.e. rotation angle for the
direct-quadrature space vector transformation (*without* considering the
rotor bias angle) so that injecting d-axis current into the stator winding
generates a cosinusoidal airgap flux
density waveform (first peak of fundamental at y = 0, assuming
non-salient rotor).
Help for FieldWindingSpec/winding_angle is inherited from superclass POLYPHASEWINDINGSPEC

### * xy Transform to phase quantities

y = xy(this, dq, angles), where

* angles : (rotor) angles in electrical degrees.

y = xy(this, dq)
Help for FieldWindingSpec/xy is inherited from superclass POLYPHASEWINDINGSPEC

