---
layout: default
title: Circuits and Conductors
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Circuits and Conductors

In `EMDtool`, `Circuits` and `Conductors` are needed to model _currents_ - both induced eddy-currents and currents flowing in windings of all kinds. In general (a few exceptions aside), 
this is what it's briefly about:

* `Conductors` are conductive bodies in the model. Examples include a coil-side of the three-phase winding of a stator,
a rotor bar, or a permanent magnet. The type of the conductor determines **how the conductor is modelled**.

* `Circuits` determine how different conductors are connected to each other.

## Usage example

Below, you can find a small code snippet illustration the usage of Circuits and Conductors. It is taken from the page on [geometry creation](geometry_creation.html).

```matlab
core_circuit = SheetCircuit('Rotor_core');
core_conductor = SolidConductor(core_domain);
core_circuit.add_conductor(core_conductor);
this.add_circuit(core_circuit);
```

In the example, we are creating a `SheetCircuit` to model the induced eddy currents in the solid rotor core of an induction motor. Specifically, you see the following steps:

1. Creating the Circuit object.

1. Creating a solid Conductor of the rotor core `Domain`.

1. Adding the conductor to the Circuit.

1. Adding the Circuit to the geometry template `this` (in this case, a `SynRotorBase` subclass).

Next, we will learn a little about the different types of Circuits and Conductors.

# Conductors in `EMDtool`

All conductors are subclasses of the [`Conductor`](../../api/Conductor.html) base class. The commonly-used ones include:

## SolidConductor

The `SolidConductor` class is used for modelling solid conductors. Solid conductors can have eddy currents induced in them - in time-stepping analysis only.

If they are part of a phase circuit (or in general, a `PolyphaseCircuit`), solid conductors can also be used in static analysis.

## StrandedConductor

`StrandedConductors` are modelled as _infinitely stranded_ - meaning the current density inside them is uniform. As such, they are pretty much exclusively used to model windings, most commonly 
phase windings or excitation coils. Using them to model eddy currents would make no sense, as a 'uniform eddy current' is by definition zero.

## SplitConductor

'SplitConductors' are a special case. They are used for such geometries where a **conducting body crosses extends beyond the modelled sector of a machine**. 

For instance, consider a high-speed surface-PM motor, with stainless steel blocks between the permanent magnets. A common approach would be to model only one pole of the rotor. In this case, however, the polegap 
pieces extend beyond the modelled region. In fact, the clockwise side of the polegap is seen on the counter-clockwise side of the modelled sector, and vice versa.

In this case, the polegap pieces should be modelled as `SplitConductors`.

**NOTE:** If the conducting body covers the entire cross-section of the machine (such as a solid shaft would), a `SheetCircuit` should instead be used.

# Circuits in `EMDtool`

The most common Circuit types are listed below.

## BlockCircuit

A `BlockCircuit` is used to model conductors that are galvanically isolated from each other. For instance, the permanent magnets inside an IPM rotor would belong to a `BlockCircuit`.

Only `SolidConductors` should be used.

## ExtrudedBlockCircuit

The 'ExtrudedBlockCircuit' is used to model solid conductors via a hybrid 2D-3D model. The magnetic field is assumed purely 2-dimensional, while the electric potential is modelled in 3D. The main purpose is 
to approximately include the effect of finite axial length; mainly axial segmentation of permanent magnets.

Perhaps About to be deprecated
{: .label .label-yellow }

To unify the behaviour, this class should probably be replaced by a new `ExtrudedSolidConductor` class, to be used with `BlockCircuit`.

## SheetCircuit

A `SheetCircuit` is used to model solid conductors that encompass the entire machine cross-section. Examples include:

* A solid shaft

* A solid housing

* Copper coat of a high-speed induction motor

The main difference between a `SheetCircuit` and a `BlockCircuit`-`SolidConductor` combo is related to some mathematics:

* In a `BlockCircuit`, the net induced (axial) current is zero inside each conductor

* A ´SheetCircuit` often has only one conductor; for instance the part of shaft falling inside one pole-pitch (we don't usually model the entire cross-section, remember). In this case, the net current inside 
the _entire shaft_ is forced to zero. However, the part of the shaft that is actually modelled and meshed _might_ have a non-zero induced current.

Perhaps About to be deprecated
{: .label .label-yellow }

To unify the behaviour, this class should probably be replaced by a new `SheetConductor` class, to be used with `BlockCircuit`.

## PolyphaseCircuit

`PolyphaseCircuits` are used to model windings of different kinds. They (more or less, some bugs aside) support both `SolidConductors` and `StrandedConductors`.

Please see the dedicated [`PolyphaseCircuit` page](polyphase_circuits.html) for more details.


## CageCircuit

A class for modelling squirrel-cages.

Perhaps About to be deprecated
{: .label .label-yellow }

To unify the behaviour, this class should probably be replaced by a `PolyphaseCircuit`, used with a new `CageWindingSpec` class.