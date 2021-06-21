---
title: Reference page for MotorModelBase
---

## Summary

MotorModelBase Base class for magnetics models.

Default construction:

motor = MotorModelBase(dimensions, stator, rotor), with

* dimensions : struct

* stator : a <StatorBase> object

* rotor : a rotor / <GeoBase> object

Detailed construction:

motor = MotorModelBase(dimensions);

motor.add_component(c1, component_name);

motor.add_component(c2, component_name);

motor.add_component(c3, component_name);

motor.add_airgap(static_part, moving_part);

motor.set_outer_boundary(bnd);

motor.finalize();

Documentation for MotorModelBase
doc MotorModelBase

# PROPERTIES
 * MotorModelBase/Ne_component is a property.
 
 * MotorModelBase/Np_component is a property.
 
 *  PMs - permanent magnets
 
 *  airgap - airgap container
 
 * MotorModelBase/boundaries is a property.
 
 *  circuits - circuits
 
 *  components - geometries making up this
 
 *  materials - materials
 
 * MotorModelBase/mesh is a property.
 
 * MotorModelBase/periodicityCoeff is a property.
 
 * MotorModelBase/ri_component is a property.
 
 *  rotor - array of moving components
 
 *  stator - array of static components
 
 * MotorModelBase/symmetrySectors is a property.
 
