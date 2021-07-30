---
title : WindingLayout
parent: API
grand_parent : Documentation
---
## Summary
WindingLayout Factory class for winding layout matrices.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * WindingLayout Factory class for winding layout matrices.

### * concentrated Concentrated winding synthesis function.

W = synthetize_winding(Q, p, m, nlayers) synthesizes a winding
configuration matrix for a tooth-wound winding.

Input arguments:
- Q : number of slots
- p : number of poles
- m : number of phases
- nlayers : number of winding layers.

Returns:
- W : winding configuration matrix. nan if winding not viable.

Based on the approach 'Synthesis of High Performance PM Motors With
Concentrated Windings'.

(c) Antti Lehikoinen / Smeklab Ltd. All rights reserved.

### * from_Emetor Parse layout matrix from Emetor string.

