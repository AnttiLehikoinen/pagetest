---
title : ExtrudedBlockCircuit
parent: API
grand_parent : Documentation
---
## Summary
ExtrudedBlockCircuit methods:
ExtrudedBlockCircuit - is a class.
get_matrices - Get circuit matrices for a particular problem
init - Initialize matrices etc. for circuit.
losses - parsing inputs
## PROPERTIES
* ExtrudedBlockCircuit/block_height is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * ExtrudedBlockCircuit/ExtrudedBlockCircuit is a constructor.

### * get_matrices Get circuit matrices for a particular problem

### * get_ndof Number of dofs associated with the circuit, for the given
problem and type.

Nui = get_ndof(this, problem, type, pars), where

* problem = [MagneticsProblem](MagneticsProblem.html) or similar

* type = string, usually "static" / "harmonic" / "stepping"
Help for ExtrudedBlockCircuit/get_ndof is inherited from superclass CIRCUITBASE

### * init Initialize matrices etc. for circuit.

### * parsing inputs

