---
title : LinearGeoBase
parent: API
grand_parent : Documentation
---
## Summary
LinearGeoBase methods:
LinearGeoBase - is a class.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * LinearGeoBase/LinearGeoBase is a constructor.
this = LinearGeoBase

### * copy_domain Copy domain and apply necessary rotations or
translations.

new = copy_domain(this, old_domain, sector_shift)

DEFAULT behaviour: rotate domain remanence and orientation
directions, if any, by sector_shift.

### * parse_nodes Parse special nodes.

parse_nodes(this, Surfaces)

Parses special nodes from meshed Surfaces. Usually airgap
and periodic boundary nodes.
Help for LinearGeoBase/parse_nodes is inherited from superclass GEOBASE

### * shift_elementary_nodes Replicate nodes to a new sector.

pnew = shift_elementary_nodes(this, p, k)

Replicated the nodes p of the elementary symmetry sector into
the sector k.
Help for LinearGeoBase/shift_elementary_nodes is inherited from superclass GEOBASE

