---
title : AirgapContainer
parent: API
grand_parent : Documentation
---
## Summary
AirgapContainer Container class for one or more airgap models.

this = AirgapContainer( model )
## PROPERTIES
* airgaps - array of airgaps

* model - parent model

## Methods
Class methods are listed below. Inherited methods are not included.
### * AirgapContainer Container class for one or more airgap models.

this = AirgapContainer( model )

### * add_gap Add an airgap.

add_gap(this, static_object, moving_object), where

* static_object : Stator-like boundary of airgap. EITHER a [GeoBase](GeoBase.html)
object, in which case airgap boundary nodes are taken from
static_object.n_ag, OR a [Boundary](Boundary.html) object.

### * AirgapContainer/finalize is a function.
finalize(this)

### * AirgapContainer/fluxplot is a function.
fluxplot(this, A, rotorAngle, potentials)

### * AirgapContainer/get_airgap_matrix is a function.
Sag = get_airgap_matrix(this, rotorAngle, varargin)

