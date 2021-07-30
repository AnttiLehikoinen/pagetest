---
title : DistributedWindingSpec
parent: API
grand_parent : Documentation
---
## Summary
DistributedWindingSpec Winding specification class for distributed
windings.

See PolyphaseWindingSpec for more details.
## PROPERTIES
* c - short-pitching; number of slot pitches

* DistributedWindingSpec/layer_direction is a property.

* half_of_turn_length

* q - number of slots per pole and phase

* DistributedWindingSpec/type is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * DistributedWindingSpec Winding specification class for distributed
windings.

See PolyphaseWindingSpec for more details.

### * end_winding_loop_matrix Loop matrix for end-winding segments.

### * set_layout_matrix Initialize winding layout matrix.

A layout matrix is a number_of_layers x number_of_slots matrix of
integers, with values in range -phases...phases.

The entries of the layout matrix W are:

*  W(i, j) = +k : phase k goes through layer i, slot j, to
positive direction:

* W(i, j) = -k : phase k goes through layer i, slot j, to
negative direction:
Help for DistributedWindingSpec/set_layout_matrix is inherited from superclass POLYPHASEWINDINGSPEC

