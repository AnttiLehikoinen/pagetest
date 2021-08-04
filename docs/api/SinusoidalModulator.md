---
title : SinusoidalModulator
parent: API
grand_parent : Documentation
---
## Summary
SinusoidalModulator Sinusoidal voltage modulator.
## PROPERTIES
* SinusoidalModulator/Udq is a property.

* SinusoidalModulator/f is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SinusoidalModulator Sinusoidal voltage modulator.

### * U(this, t) Instantaneous voltage.

Uterminal = U(this, t, varargin) returns the terminal *potentials*  measured
against an arbitraty reference point. For instance, for the
typical 3-phase inverter bridge, the output would be a 3x1 vector
of the output voltages of each half-bridge, measured agains the
"ground".
Help for SinusoidalModulator/U is inherited from superclass MODULATOR

### * RESET  Reset graphics object properties to their defaults.
RESET(H) resets all properties having factory defaults on the object
identified by handle H to their default values. If h is a figure, MATLAB
does not **reset** PaperPosition, PaperUnits, Position, Units or WindowStyle.
If h is an axes, MATLAB does not **reset** Position and Units.

For example,
RESET(GCA) resets the properties of the current axis.
RESET(GCF) resets the properties of the current figure.

See also CLA, CLF, GCA, GCF, HOLD.

### * set_Udq Set supply voltage components

set_Udq(this, Udq)
Help for SinusoidalModulator/set_Udq is inherited from superclass MODULATOR

### * set_f Set fundamental supply frequency.

set_f(this, f)
Help for SinusoidalModulator/set_f is inherited from superclass MODULATOR

