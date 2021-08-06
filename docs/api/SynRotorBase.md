---
title : SynRotorBase
parent: API
grand_parent : Documentation
---
## Summary
SynRotorBase Base class for synchronous machine rotors.

This class doesn't contain any geometry-creation functionality
(this.mesh_geometry). Symmetry sector angles etc. are determinated
from the number of pole pairs (dimensions.p) and number of symmetry sectors
(dimensions.symmetry_sectors).

Permanent magnet orientation is reversed for each successive pole,
along with rotation according to this.sector_angle.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * Nrep Number of times to replicate elementary mesh.

Nrep(this)

Usually subclassed, but by default returns
this.dimensions.Nrep.
Help for SynRotorBase/Nrep is inherited from superclass GEOBASE

### * SynRotorBase/SynRotor is a function.
this = SynRotor(dim)

### * SynRotorBase Base class for synchronous machine rotors.

This class doesn't contain any geometry-creation functionality
(this.mesh_geometry). Symmetry sector angles etc. are determinated
from the number of pole pairs (dimensions.p) and number of symmetry sectors
(dimensions.symmetry_sectors).

Permanent magnet orientation is reversed for each successive pole,
along with rotation according to this.sector_angle.

### * SynRotorBase/d_axis_angle is a function.
y = d_axis_angle(this)

### * sector_angle Angle of symmetry sector.

sector_angle(this)

Usually subclassed, but by default returns
this.dimensions.sector_angle.
Help for SynRotorBase/sector_angle is inherited from superclass RADIALGEOMETRY

### * symmetry_period Symmetry period of the geometry.

symmetry_period(this)

Usually subclassed, but by default returns
this.dimensions.symmetry_period.
Help for SynRotorBase/symmetry_period is inherited from superclass GEOBASE

