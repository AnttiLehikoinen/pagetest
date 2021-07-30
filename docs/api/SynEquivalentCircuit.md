---
title : SynEquivalentCircuit
parent: API
grand_parent : Documentation
---
## Summary
SynEquivalentCircuit methods:
SynEquivalentCircuit - is a class.
from_model - Instantiate equivalent circuit for model.
get_max_torque - Compute maximum attainable torque.
get_max_torque_NOT_WORKING - get_max_torque Compute maximum attainable torque.
get_op_FW - initial guess
get_op_MTPA - initial guess
save_to_excel - Save eq. circuit parameters to Excel.
simulate_SVPWM -
## PROPERTIES
* LM - inductance matrix

* LM_ew - end-winding part of inductance

* Phi - flux vector

* R - resistance

* Umax - Max phase peak voltage

* SynEquivalentCircuit/angle is a property.

* fs - switching frequency

* SynEquivalentCircuit/id0 is a property.

* SynEquivalentCircuit/iq0 is a property.

* p - number of pole-pairs

* phases - number of phases

## Methods
Class methods are listed below. Inherited methods are not included.
### * SynEquivalentCircuit/SynEquivalentCircuit is a constructor.
this = SynEquivalentCircuit(R, Phi, LM, p, varargin)

### * SynEquivalentCircuit/constant_voltage_vector is a function.
phi = constant_voltage_vector(this, n)

### * SynEquivalentCircuit/current_from_voltage is a function.
i = current_from_voltage(this, n, ud, uq)

### * from_model Instantiate equivalent circuit for model.

circuit = from_model(model)

Initialize using default settings (see below).

circuit = from_model(model, key1, val1, ...)

Initialize with any of the following key-value pairs:

* 'idq', idq : compute parameters at the specified (id,iq) point.
Default [0;0].

* 'angles', angles : Vector of electrical angles (rad) to average
eq. circuit parameters over. Default linspace(0, 2*pi/6, 10).

* Any key-value pair of compute_inductances_static_averaging
(default mode: differential)

* Any key-value pair of SynEquivalentCircuit

### * get_max_torque Compute maximum attainable torque.

[id, iq, Ed, Eq] = get_max_torque(this, n)

Compute maximum torque at the speed n, while utilizing the full
available voltage. Bisection search used.

### * get_max_torque Compute maximum attainable torque.

[id, iq, Ed, Eq] = get_max_torque(this, n)

Compute maximum torque at the speed n, while utilizing the full
available voltage. Sequential Quadratic Programming approach used.

### * get_op Iterate operating point.

[id, iq, Ed, Eq, mode] = get_op(this, n, T)

### * initial guess

### * initial guess

### * SynEquivalentCircuit/impedance_matrix is a function.
Z = impedance_matrix(this, n)

### * SynEquivalentCircuit/loss_Hessian_wrt_voltage is a function.
ddW = loss_Hessian_wrt_voltage(this, n)

### * SynEquivalentCircuit/loss_gradient_wrt_voltage is a function.
dW = loss_gradient_wrt_voltage(this, n, ud, uq)

### * SynEquivalentCircuit/permeance_matrix is a function.
Y = permeance_matrix(this, n)

### * save_to_excel Save eq. circuit parameters to Excel.


save_to_excel(filename)

save_to_excel(filename, key, val), where

* 'sheetname', sheet_name : save to specified excel sheet. Default:
'Equivalent circuit parameters'

### * simulate_SVPWM

[idq, iripple, ts, Us] = simulate_SVPWM(this, rpm, id, iq)

[idq, iripple, ts, Us] = simulate_SVPWM(this, rpm, id, iq, ts)

### * SynEquivalentCircuit/torque is a function.
[T, Td] = torque(this, id, iq)

### * torque_Hessian Numerical Hessian matrix of torque.

### * SynEquivalentCircuit/torque_gradient is a function.
dT = torque_gradient(this, id, iq)

### * SynEquivalentCircuit/torque_gradient_wrt_voltage is a function.
dT = torque_gradient_wrt_voltage(this, n, ud, uq)

### * SynEquivalentCircuit/update is a function.
this = update(this, Phi, LM, varargin)

### * VOLTAGE Voltage

[Ud, Uq, Udq] = VOLTAGE(this, n, id, iq)

### * SynEquivalentCircuit/voltage_norm is a function.
U = voltage_norm(this, n, id, iq)

### * SynEquivalentCircuit/voltage_norm_Hessian is a function.
ddU = voltage_norm_Hessian(this, n, id, iq)

### * SynEquivalentCircuit/voltage_norm_gradient is a function.
dU = voltage_norm_gradient(this, n, id, iq)

### * SynEquivalentCircuit/voltage_squared_Hessian is a function.
ddU = voltage_squared_Hessian(this, n, id, iq)

### * SynEquivalentCircuit/voltage_squared_gradient is a function.
dU = voltage_squared_gradient(this, n, id, iq)

