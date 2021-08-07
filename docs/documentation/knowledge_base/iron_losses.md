---
layout: default
title: Iron loss modelling
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Iron loss modelling in finite-element analysis

## Frequency-domain Bertotti model

$$ p = \sum\limits_{n=1}^N c_\text{hysteresis} f_n B_n^2 + c_\text{eddy} (f_n B_n)^2 \quad \left( + c_\text{excess} (f_n B_n)^{1.5} \right) $$

Text

## Time-domain Steinmetz model

$$ p(t) = c_\text{hysteresis} \left| B(t) \right|^a  \left| \frac{\text{d}B(t)}{\text{d}t} \right|^b +  c_\text{eddy} \left( \frac{\text{d}B(t)}{\text{d}t} \right)^2 $$

moarrr text 