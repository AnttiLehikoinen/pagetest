---
title : SlottedRotorBase
parent: API
grand_parent : Documentation
---
## Summary
SlottedRotorBase Base class for slotted radial-flux rotors.

This class doesn't contain any geometry-creation functionality
(this.mesh_geometry). Symmetry sector angles etc. are determinated
from the slot number (dimensions.Qr) and number of symmetry sectors
(dimensions.symmetry_sectors).
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * Nrep Number of times to replicate elementary mesh.

Nrep(this)

Usually subclassed, but by default returns
this.dimensions.Nrep.
Help for SlottedRotorBase/Nrep is inherited from superclass GEOBASE

### * SlottedRotorBase Base class for slotted radial-flux rotors.

This class doesn't contain any geometry-creation functionality
(this.mesh_geometry). Symmetry sector angles etc. are determinated
from the slot number (dimensions.Qr) and number of symmetry sectors
(dimensions.symmetry_sectors).

### * SlottedRotorBase/d_axis_angle is a function.
a = d_axis_angle(~)

### * sector_angle Angle of symmetry sector.

sector_angle(this)

Usually subclassed, but by default returns
this.dimensions.sector_angle.
Help for SlottedRotorBase/sector_angle is inherited from superclass RADIALGEOMETRY

