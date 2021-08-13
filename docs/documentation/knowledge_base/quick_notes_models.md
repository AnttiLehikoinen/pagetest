---
layout: default
title: Quick Notes - Models and Geometries
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

#  Geometry and Models in EMDtool: Quick notes

As a rough summary, model creation for `EMDtool` happens in three levels of abstraction:

* Raw geometry level: [Points](../../api/Point.html), [Curves](../../api/Curve.html), and [Surfaces](../../api/Surface.html)

* [Component](../../api/GeoBase.html) leve: stator and rotor model components, for
example

* 'Motor level': For example the [MotorModelBase](../../api/MotorModelBase.html) and [RFmodel](../../api/RFmodel.html) classes.

# Raw geometry representation

Geometries in `EMDtool` are represented with 3 classes:

* [Points](../../api/Point.html): points in 2D.

* [Curves](../../api/Curve.html): lines or arcs, joining 2 Points (arcs also have a
center.

* [Surfaces](../../api/Surface.html): 2D surfaces bounded by Curves.

Important details and notes:

* Each Point has a _characteristic length_ representing mesh density (=
maximum edge length) around that point.

* Points must be unique, i.e. be careful not to create 2 points with the
same coordinates.

* Arcs must be strictly less than 180 degrees in span. For longer arcs, you'll have to split them into 2-3 smaller Arcs.

* Curves and surfaces must obviously be unique, too.

* Curves cannot intersect. Instead, the intersection has to be defined as
Point, and new Curves created.

* **To emphasize**: The only Points the are allowed to lie on a curve
are its start and end points. Anything else will result in a faulty
geometry.

* In other words, any T-shaped junction must consist of _three_ lines at
minimum, not two. Likewise, shorter curve can't lie on top of a longer
one; instead the geometry must be divided into multiple non-overlapping
curves.

* Often, you don't have to create Curves by hand. Instead, you can use
the `Surface.add_curve` method like this: `surf.add_curve(geo.line,
Point_start, Point_end)` or `surf.add_curve(geo.arc, Point_start, Point_center,
Point_end)`. This method automatically either uses an existing unique Curve, or
creates a new one if needed.

* Often, you will have _surfaces inside surfaces_, such as a permanent
magnet inside the rotor core. The inner surface *must* be specified as a
_hole_ for the _outer_ surface, otherwise meshing will fail. This can be
done by `core_surface.add_curve(geo.hole, magnet_surface)` or
`core_surface.add_hole(magnet_surface)`.

* Due to meshing limitations, holes should not share any Curves with the
Surface. If they do, meshing often fails (but not always). In this case,
the Surface should be specified in such a fashion that there are no
holes.

* As the above is tedious, the experimental method `surface.reduce` can
help. Informally expressed: you give a Curve segment to the method to start with, and it clips away all the holes that on the Surface boundaries.

# Higher-level geometry objects

In practice, you will most of the time work with higher-level geometry objects;
subclasses of the [GeoBase](../../api/GeoBase.html) class. These encapsulate all the
components and functionality of e.g. a stator model under one object:

* `stator.dimensions` : dimensions as a struct

* `stator.domains` : each [Domain](../../api/Domain.html) consists of a single material
and one or more surfaces.

* `stator.materials` : [Materials](../../api/MaterialBase.html) used.

* `stator.circuits` : <[Circuits](../../api/CircuitBase.html) defined for the
geometry. A circuit has one or more [Conductors](../../api/ConductorBase.html).

* Methods for mesh creation and replication

Geometry objects take most of the meshing trouble out of your hands; see
the next points. In practice, it is recommended to subclass one of the geometry
base classes ([StatorBase](../../api/StatorBase.html), [SlottedRotorBase](../../api/SlottedRotorBase.html),
[SynRotorBase](../../api/SynRotorBase.html) ...). For quick
testing, the [RadialGeometry](../../api/RadialGeometry.html) class can be used directly, see
[this example](../../api/example_2.html).

# Periodic / repeated geometries

Usually, it makes sense to only create the geometry for e.g. one rotor
pole or one stator slot pitch only. In this case, the resulting mesh will
be automatically replicated accordingly. For this to work, 

* _Periodic boundaries_ must be specified with `geo.set_periodic` while
creating the geometry.

* Geometry replication functionality is encapsulated under the abstract
class GeoBase.

# Airgap surface

By default, Curves on the airgap surface (such as the outer surface of a
normal inrunner rotor) should be named 'n_ag'.

# Meshing

In practice calling the `.mesh_geometry` method is enough. Underneath,
this method successively calls the `.mesh_elementary_geometry` and
`.replicate_elementary_mesh` methods, which do exactly what the name
suggests.

# High-level Model objects.

Finally, the individual components such as a `stator` and a `rotor` would
be wrapped under a Model object, most commonly a [RFmodel](../../api/RFmodel.html)
Let's call it `motor`. But why the third level of complication?

Well, the actual analysis/simulation tasks are usually not handcoded;
instead the handy [MagneticsProblem](../../api/MagneticsProblem.html) class is used.
By wrapping all the motor-related information - the 'personality' of the
motor inside the `motor` object, the same `problem` can be used to
analyse very different motor topologies, say

* Normal radial-flux inrunner

* Sliced models

* An outrunner PM motor with an additional aluminum outer frame with eddy
currents

* etc...