---
title : SVPWM_Modulator
parent: API
grand_parent : Documentation
---
## Summary
SVPWM_Modulator Basic Modulator.


Instantiation:

this = SVPWM_Modulator(UDC, fs), where

* UDC = DC-link voltage

* fs = switching frequency
## PROPERTIES
* SVPWM_Modulator/TPWM is a property.

* SVPWM_Modulator/Tp is a property.

* SVPWM_Modulator/U0 is a property.

* SVPWM_Modulator/U1 is a property.

* SVPWM_Modulator/U2 is a property.

* SVPWM_Modulator/U3 is a property.

* SVPWM_Modulator/U4 is a property.

* SVPWM_Modulator/U5 is a property.

* SVPWM_Modulator/Uangles is a property.

* SVPWM_Modulator/Ubus is a property.

* SVPWM_Modulator/Uref is a property.

* SVPWM_Modulator/Uvectors is a property.

* SVPWM_Modulator/f1 is a property.

* SVPWM_Modulator/t0 is a property.

* SVPWM_Modulator/t1 is a property.

* SVPWM_Modulator/t2 is a property.

* SVPWM_Modulator/t3 is a property.

* SVPWM_Modulator/t4 is a property.

* SVPWM_Modulator/t5 is a property.

* SVPWM_Modulator/t6 is a property.

* SVPWM_Modulator/ts is a property.

* SVPWM_Modulator/uvectors is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SVPWM_Modulator Basic Modulator.


Instantiation:

this = SVPWM_Modulator(UDC, fs), where

* UDC = DC-link voltage

* fs = switching frequency

### * U(this, t) Instantaneous voltage.

Uterminal = U(this, t, varargin) returns the terminal *potentials*  measured
against an arbitraty reference point. For instance, for the
typical 3-phase inverter bridge, the output would be a 3x1 vector
of the output voltages of each half-bridge, measured agains the
"ground".
Help for SVPWM_Modulator/U is inherited from superclass MODULATOR

### * getting reference voltage vector

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
Help for SVPWM_Modulator/set_Udq is inherited from superclass MODULATOR

### * set_f Set fundamental supply frequency.

set_f(this, f)
Help for SVPWM_Modulator/set_f is inherited from superclass MODULATOR

