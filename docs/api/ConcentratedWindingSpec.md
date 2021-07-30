---
title : ConcentratedWindingSpec
parent: API
grand_parent : Documentation
---
## Summary
ConcentratedWindingSpec methods:
ConcentratedWindingSpec - is a class.
end_winding_loop_matrix - ConcentratedWindingSpec/end_winding_loop_matrix is a function.
get_half_of_turn_length - ConcentratedWindingSpec/get_half_of_turn_length is a function.
get_overhang_length - ConcentratedWindingSpec/get_overhang_length is a function.
## PROPERTIES
* ConcentratedWindingSpec/layer_direction is a property.

* overhang_length - winding overhang length
Help for ConcentratedWindingSpec/overhang_length is inherited from superclass POLYPHASEWINDINGSPEC

* ConcentratedWindingSpec/q is a property.

* ConcentratedWindingSpec/type is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * ConcentratedWindingSpec/ConcentratedWindingSpec is a constructor.
this = ConcentratedWindingSpec(varargin)

### * end_winding_loop_matrix End-winding loop matrix, slot-segment.

L = end_winding_loop_matrix(this)

Returns a number_of_slots x phases matrix, representing how many
times each phase traverses each 'slot segment' = end-winding
piece between two successive slots.

Only computed for one end of a radial-flux machine.
Help for ConcentratedWindingSpec/end_winding_loop_matrix is inherited from superclass POLYPHASEWINDINGSPEC

### * set_layout_matrix Initialize winding layout matrix.

A layout matrix is a number_of_layers x number_of_slots matrix of
integers, with values in range -phases...phases.

The entries of the layout matrix W are:

*  W(i, j) = +k : phase k goes through layer i, slot j, to
positive direction:

* W(i, j) = -k : phase k goes through layer i, slot j, to
negative direction:
Help for ConcentratedWindingSpec/set_layout_matrix is inherited from superclass POLYPHASEWINDINGSPEC

