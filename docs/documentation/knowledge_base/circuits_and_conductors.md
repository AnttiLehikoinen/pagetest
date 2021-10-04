---
layout: default
title: Circuits and Conductors
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Circuits and Conductors

This page introduces you to the concepts of circuits and conductors in EMDtool. In general (a few exceptions) aside, 
this is what it's briefly about:

* `Conductors` are conductive bodies in the model. Examples include a coil-side of the three-phase winding of a stator,
a rotor bar, or a permanent magnet. The type of the conductor determines **how the conductor is modelled**.

* `Circuits` determine how different conductors are connected to each other.

## Usage example

Creation of conductors and circuits is quite simple.

```matlab
core_circuit = SheetCircuit('Rotor_core');
core_conductor = SolidConductor(core_domain);
core_circuit.add_conductor(core_conductor);
this.add_circuit(core_circuit);
```

# Circuits

# Conductors