---
layout: default
title: Polyphase Circuits
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Polyphase Circuits

`PolyphaseCircuits` are used to model windings - several Conductors, connected to each other outside the 2D-domain via an end-winding, and supplied with one of numerous options.

Under simulation/analysis, the behaviour of a `PolyphaseCircuit` depends on several factors:

* Type of `Conductors`

* Type of supply

* Type of winding

The following sections will briefly cover each of these.


# Conductors

A PolyPhaseCircuit may consist of either `StrandedConductors` or `SolidConductors`. Mixing several conductor types into one winding should work, but is currently untested. Please see 
[this page](circuits_and_conductors.html) for the differences between Circuits and Conductors.

Typically, 'SolidConductors' are used for hairpin or other form-wound windings. 

Correspondingly, 'StrandedConductors' are most commonly used for random-wound windings, with dozens or hundreds of individual wires per slot, to avoid meshing and modelling each of them. Please note that
this _can_ be done - it is simply time-consuming and results in long simulation times.

Smeklab Ltd **does** possess the know-how to greatly speed-up simulation of explicitly-meshed random windings - this is simply currently not implemented in `EMDtool`.

# Supply

A PolyphaseCircuit must be supplied in one of the supported ways, by calling the `.set_source(type, args...)` method.

* Imposing a fixed current density (`uniform coil current` keyword `type`).

* Imposing the net terminal current (`terminal current source`). If the winding is modelled as stranded, coil current densities will be uniform, but there could be a zero-sequence current flowing,
depending on the winding configuration. If the winding is modelled as solid, current densities are also solved.

* Imposing a voltage on the winding terminals (`terminal voltage`). Otherwise as above.

* Having a dedicated, generally non-linear time-variant electrical circuit connected to the terminals (`circuit`). **UNDER CONSTRUCTION**

# Winding specification

The `PolyphaseCircuit` class is mostly a creature of finite element analysis. Thus, its responsibilities mostly include assembling and returning matrices and vectors for all the different analysis types
one can think of.

To keep things simpler, the `PolyphaseCircuit` class then relies on a _**winding specification**_ class (a subclass of 
the [`PolyphaseWindingSpec`](../../api/PolyphaseWindingSpec.html) class) to keep track of all the mostly-motor-design related information.

For instance, the `PolyphaseCircuit` does not care if the winding in question is a distributed winding or concentrated, let alone if a distributed winding is of a lap, a wave, or a hairpin type. The
finite-element part of the modelling is _exactly_ the same, allowing the same `PolyPhaseCircuit` to be used to model all of the aforementioned different physical winding types.

Indeed, it is then the responsibility of the `PolyphaseWindingSpec` object to tell to the `PolyphaseCircuit` all the engineering information that is actually needed for modelling, such as:

* How the different conductors are connected to each other

* How long the end-winding conductors are

* End-winding inductance matrix

* The fill factor of the winding (in case of stranded conductors)

* A few key numbers, such as the number of meshed conductors per winding layer.

For more information, see the dedicated [winding specification page](winding_specifications.html).


# Winding issues

UNDER CONSTRUCTION
{: .label .label-red }

## Custom windings

* Double-check the matrix returned by your winding specification object (most likely a subclass of [PolyphaseWindingSpec](../../api/PolyphaseWindingSpec.html)), by the `get_loop_matrix` method. Verify that
it makes sense.

## Winding specification

Why own dq? 6-phase system, either true (5-6 dof) or 2x3 with separate star points (2-dof)

# Stuff

How derivatives are computed

Loop matrix

L_ij = +N, loop current j goes through conductor i, N times, to the positive direction


L_ij = -N, loop current j goes through conductor i, N times, to the negative direction

0 = otherwise