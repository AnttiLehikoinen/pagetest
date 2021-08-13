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

## Winding specification

Why own dq? 6-phase system, either true (5-6 dof) or 2x3 with separate star points (2-dof)