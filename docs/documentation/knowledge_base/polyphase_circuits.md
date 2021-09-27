---
layout: default
title: Polyphase Circuits
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Winding issues

## Custom windings

* Double-check the matrix returned by your winding specification object (most likely a subclass of [PolyphaseWindingSpec](../../api/PolyphaseWindingSpec.html)), by the `get_loop_matrix` method. Verify that
it makes sense.

# Circuits

* Own page for Circuits (Block, Sheet, Polyphase, Extruded) --> then direct to PolyPhaseCircuit

## Winding specification

Why own dq? 6-phase system, either true (5-6 dof) or 2x3 with separate star points (2-dof)

# Stuff

How derivatives are computed

Loop matrix

L_ij = +N, loop current j goes through conductor i, N times, to the positive direction


L_ij = -N, loop current j goes through conductor i, N times, to the negative direction

0 = otherwise