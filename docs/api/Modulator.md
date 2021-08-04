---
title : Modulator
parent: API
grand_parent : Documentation
---
## Summary
Base class for modulators.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * Base class for modulators.

### * U(this, t) Instantaneous voltage.

Uterminal = U(this, t, varargin) returns the terminal *potentials*  measured
against an arbitraty reference point. For instance, for the
typical 3-phase inverter bridge, the output would be a 3x1 vector
of the output voltages of each half-bridge, measured agains the
"ground".

### * set_Udq Set supply voltage components

set_Udq(this, Udq)

### * set_f Set fundamental supply frequency.

set_f(this, f)

