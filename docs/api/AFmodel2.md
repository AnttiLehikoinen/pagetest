---
title : AFmodel2
parent: API
grand_parent : Documentation
---
## Summary
AFmodel2 methods:
AFmodel2 - is a class.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * AFmodel2/AFmodel2 is a constructor.

### * compute_torque Computes torque

T = compute_torque(this, solution)

Computes torque associated with the MagneticsSolution
solution.

T is of size number_of_airgaps x number_of_steps
Help for AFmodel2/compute_torque is inherited from superclass MOTORMODELBASE

### * AFmodel2/get_rotated_nodes is a function.
p = get_rotated_nodes(this, rotorAngle)

### * AFmodel2/initialize_airgap is a function.
initialize_airgap(this)

### * AFmodel2.simple is a function.
motor = simple(dim, stator, rotor)

