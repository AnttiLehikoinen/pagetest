---
layout: default
title: General tips for debugging
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Winding issues

## Custom windings

* Double-check the matrix returned by your winding specification object (most likely a subclass of [PolyphaseWindingSpec](../../api/PolyphaseWindingSpec.html)), by the `get_loop_matrix` method. Verify that
it makes sense.

