---
title : LaminatedCircuit
parent: API
grand_parent : Documentation
---
## Summary
LaminatedCircuit Class for modelling classical eddy currents in
laminated [Domain](Domain.html)s.

Modelled with the approach presented in e.g. 'Finite-Element Modeling
and Calorimetric Measurement of Core Losses in Frequency-Converter-Supplied
Synchronous Machines'.

https://aaltodoc.aalto.fi/bitstream/handle/123456789/7292/isbn9789526048864.pdf?sequence=4&isAllowed=y
## PROPERTIES
* LaminatedCircuit/sheet_thickness is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * LaminatedCircuit Class for modelling classical eddy currents in
laminated [Domain](Domain.html)s.

Modelled with the approach presented in e.g. 'Finite-Element Modeling
and Calorimetric Measurement of Core Losses in Frequency-Converter-Supplied
Synchronous Machines'.

https://aaltodoc.aalto.fi/bitstream/handle/123456789/7292/isbn9789526048864.pdf?sequence=4&isAllowed=y

### * init Initialize matrices etc. for circuit.

init(this, problem) ties this to the given [MagneticsProblem](MagneticsProblem.html) and
initializes the problem matrices and arrays in this.matrices:

* inds_solid : which of the Conductors in this are solid

* inds_stranded : likewise for stranded

* R : per-conductor resistances, active length

* R_EW : per-conductor resistances, end-winding length

* area : conductor areas

* sigma : conductor conductivities. Assumed uniform.

* M : mass/damping matrix

* C_Ai : current source matrix

* C_Au : voltage source matrix

* C_uu : voltage-voltage coupling matrix

* L : circuit loop matrix
Help for LaminatedCircuit/init is inherited from superclass CIRCUIT

### * TODO fix plotting etc

