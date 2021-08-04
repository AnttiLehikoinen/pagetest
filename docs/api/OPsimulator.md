---
title : OPsimulator
parent: API
grand_parent : Documentation
---
## Summary
OPsimulator Class for analysing operating points.
## PROPERTIES
* OPsimulator/N_DETAILED is a property.

* OPsimulator/N_PRE is a property.

* OPsimulator/UDC is a property.

* copts - set in this.reset()

* OPsimulator/current_waveform is a property.

* eqopts - set in this.reset()

* OPsimulator/fs is a property.

* modulator - FIXME refactor into single input

* OPsimulator/periods_detailed is a property.

* OPsimulator/periods_pre is a property.

* OPsimulator/simulation_type is a property.

* OPsimulator/supply_mode is a property.

* OPsimulator/verbose is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * OPsimulator Class for analysing operating points.

### * OPsimulator/dispf is a function.
dispf(this, msg)

### * get_max_torque_eq Maximum torque at given rpm, from eqcircuit.

[id, iq, U] = get_max_torque_eq(this, rpm)

### * OPsimulator/get_op is a function.
[solution, id, iq, T0, U0, data] = get_op(this, Ttarget, rpm)

### * OPsimulator/get_op_FW is a function.
[solution, id, iq, Tnow, Unow] = get_op_FW(this, Ttarget, rpm, id, iq, Tnow, Unow)

### * OPsimulator/get_op_MTPA is a function.
[solution, id, iq, Tnow, Unow] = get_op_MTPA(this, Ttarget, rpm, id, iq, Tnow)

### * get_op_eq Iterate rough operating point with equivalent circuit.

### * init_current_ripple Initialize current ripple.

init_current_ripple(this, id, iq, rpm) Sets current ripple if not
*already*  set.

### * init_detailed Initialize for detailed FEA computation.

[T, U, solution] = init_detailed(this, id, iq, rpm)

- calculate equivalent circuit parameters with DETAILED accuracy
settings.

- set current ripple waveform if needed.

### * RESET  Reset graphics object properties to their defaults.
RESET(H) resets all properties having factory defaults on the object
identified by handle H to their default values. If h is a figure, MATLAB
does not **reset** PaperPosition, PaperUnits, Position, Units or WindowStyle.
If h is an axes, MATLAB does not **reset** Position and Units.

For example,
RESET(GCA) resets the properties of the current axis.
RESET(GCF) resets the properties of the current figure.

See also CLA, CLF, GCA, GCF, HOLD.

### * simulate_op Simulate operating point.

[T, U, solution] = simulate_op(this, id, iq, rpm)

- Simulates given operating point with the DETAILED precision settings.

- Updates equivalent circuit parameters.

