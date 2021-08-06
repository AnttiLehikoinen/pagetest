---
title : WindingLayoutBase
parent: API
grand_parent : Documentation
---
## Summary
WindingLayoutBase Base class for winding layouts.

The WindingLayoutBase class exists to simplify the workflow of
creating the *winding*  part of slot geometries, such as creating the
necessary [Material](Material.html)s, [Surface](Surface.html)s, and [Domain](Domain.html)s, adding [Conductor](Conductor.html)s
to the parent [PolyphaseCircuit](PolyphaseCircuit.html), and so on.

Where the [PolyphaseWindingSpec](PolyphaseWindingSpec.html) handles the overall winding layout,
the [WindingLayoutBase](WindingLayoutBase.html) class focuses on everything that goes on
inside the slot itself.

Ideally, the WindingLayoutBase class is used as follows. When
creating the parent geometry (see [Stator](Stator.html).create_geometry), only the
[Surface](Surface.html)(s) for the winding layers are created. This can be done
manually, or handled automatically by a [SlotShapeBase](SlotShapeBase.html) object.

Then, either the [Surface](Surface.html)s or the [SlotShapeBase](SlotShapeBase.html) object is passed
on to `WindingLayoutBase.create_slot_geometry` , along with the parent
geometry (e.g. [Stator](Stator.html) object) and the <PolyphaseWindingSpec|
object.

The `create_slot_geometry`  method then

* Creates all the [Material](Material.html)s associated with the winding (e.g.
conductor material) and adds them to the parent geometry.

* Creates the required [Domains](Domains.html) and required Surfaces, and adds them
to the parent geometry.
* By default, if the winding model
type ( `winding_model_type`  property of the winding spec) is
defs.stranded|, one Domain is created for each surface.
* If the model is `defs.solid` , individual conductors (such as
wires or bars) are created as new Surfaces and Domains. This
functionality has to be subclassed.

* Creates the required [Conductor](Conductor.html)s and adds them to the parent
geometry. By default, only [StrandedConductor](StrandedConductor.html) or [SolidConductor](SolidConductor.html)
objects are created.

Finally, the WindingLayoutBase object contains an implementation for
estimating AC conductor losses of stranded winding models. As this
depends on the conductor shape (and the very mathematical
approximation preferred), this funcionality has to be subclassed.

NOTE: you don't *have*  to use a WindingLayoutBase object. Indeed, it
is totally fine to create all the required Surfaces, Materials,
Domains, and Conductors manually in the `create_geometry`  method of
your parent geometry. (This might result in errors though - please contact
the support if this happens.)

However, the class is intended for maximizing
the reusability and interchangeability of, well, everything. For
instance, if you are creating a new [StatorBase](StatorBase.html) subclass for some
purpose, you don't then have to separately implement functionality
for modelling stranded conductors, solid bar conductors, solid wires,
... - you get the point. Instead, you can externalize that tedium to
the suitable WindingLayoutBase object.

Finally, a `WindingLayoutBase`  object can be used to easily set the
slot liner thickness and to access to uninsulated winding area, to
evaluate packing factors etc.

USAGE: The intended usage is as follows.

**Simple case**  : While specifying the dimensions, you set the
`layout_spec`  property of your winding spec to the layout you prefer.

*Custom case: : While creating a custom parent geometry, you either
use a [SlotShapeBase](SlotShapeBase.html) object and pass it on to the
`create_slot_geometry`  method, or you manually create the slot (or
rather, winding) [Surfaces](Surfaces.html), and pass them as an array.
## PROPERTIES
* interlayer_insulation_length - linear interlayer insulation length

* interlayer_insulation_thickness Interlayer insulation thickness.

If not specified, slot liner thickness x 2 is returned.

* slot - a [SlotShapeBase](SlotShapeBase.html) object associated with this

* slot_liner_length - linear slot liner length

* slot_liner_thickness - slot liner thickness (m)

* winding_window_area - winding window area, gross

## Methods
Class methods are listed below. Inherited methods are not included.
### * WindingLayoutBase Base class for winding layouts.

The **WindingLayoutBase** class exists to simplify the workflow of
creating the *winding*  part of slot geometries, such as creating the
necessary [Material](Material.html)s, [Surface](Surface.html)s, and [Domain](Domain.html)s, adding [Conductor](Conductor.html)s
to the parent [PolyphaseCircuit](PolyphaseCircuit.html), and so on.

Where the [PolyphaseWindingSpec](PolyphaseWindingSpec.html) handles the overall winding layout,
the [WindingLayoutBase](WindingLayoutBase.html) class focuses on everything that goes on
inside the slot itself.

Ideally, the **WindingLayoutBase** class is used as follows. When
creating the parent geometry (see [Stator](Stator.html).create_geometry), only the
[Surface](Surface.html)(s) for the winding layers are created. This can be done
manually, or handled automatically by a [SlotShapeBase](SlotShapeBase.html) object.

Then, either the [Surface](Surface.html)s or the [SlotShapeBase](SlotShapeBase.html) object is passed
on to `WindingLayoutBase.create_slot_geometry` , along with the parent
geometry (e.g. [Stator](Stator.html) object) and the <PolyphaseWindingSpec|
object.

The `create_slot_geometry`  method then

* Creates all the [Material](Material.html)s associated with the winding (e.g.
conductor material) and adds them to the parent geometry.

* Creates the required [Domains](Domains.html) and required Surfaces, and adds them
to the parent geometry.
* By default, if the winding model
type ( `winding_model_type`  property of the winding spec) is
defs.stranded|, one Domain is created for each surface.
* If the model is `defs.solid` , individual conductors (such as
wires or bars) are created as new Surfaces and Domains. This
functionality has to be subclassed.

* Creates the required [Conductor](Conductor.html)s and adds them to the parent
geometry. By default, only [StrandedConductor](StrandedConductor.html) or [SolidConductor](SolidConductor.html)
objects are created.

Finally, the **WindingLayoutBase** object contains an implementation for
estimating AC conductor losses of stranded winding models. As this
depends on the conductor shape (and the very mathematical
approximation preferred), this funcionality has to be subclassed.

NOTE: you don't *have*  to use a **WindingLayoutBase** object. Indeed, it
is totally fine to create all the required Surfaces, Materials,
Domains, and Conductors manually in the `create_geometry`  method of
your parent geometry. (This might result in errors though - please contact
the support if this happens.)

However, the class is intended for maximizing
the reusability and interchangeability of, well, everything. For
instance, if you are creating a new [StatorBase](StatorBase.html) subclass for some
purpose, you don't then have to separately implement functionality
for modelling stranded conductors, solid bar conductors, solid wires,
... - you get the point. Instead, you can externalize that tedium to
the suitable **WindingLayoutBase** object.

Finally, a `WindingLayoutBase`  object can be used to easily set the
slot liner thickness and to access to uninsulated winding area, to
evaluate packing factors etc.

USAGE: The intended usage is as follows.

**Simple case**  : While specifying the dimensions, you set the
`layout_spec`  property of your winding spec to the layout you prefer.

*Custom case: : While creating a custom parent geometry, you either
use a [SlotShapeBase](SlotShapeBase.html) object and pass it on to the
`create_slot_geometry`  method, or you manually create the slot (or
rather, winding) [Surfaces](Surfaces.html), and pass them as an array.

### * compute_losses_stranded Estimate AC losses in stranded windings.

Estimate AC loss distribution for stranded (= non-solid)
conductor models.

[p_el, data] = compute_losses_stranded(this, winding_spec, dBx,
dBy, conductivity), where

* winding_spec : [PolyphaseWindingSpec](PolyphaseWindingSpec.html) object for specifying the
winding.

* dBx, dBy : time-derivative of flux density

* conductivity : electrical conductivity, assumed uniform.

See the code of PolyphaseCircuit.stranded_conductor_losses for
more details.

### * conductor_area Total conductor area per slot.

Returns nan by default; should be overridden in subclasses if
needed.

### * create_slot_geometry Create the winding geometry.

This method creates the winding geometry, creating the necessary
[Material](Material.html) and [Domain](Domain.html) objects and adding them to the `parent_geometry` .
In addition, it creates the required `Conductor` s specified by the
`winding_spec.winding_model_type`  property, and adds them to the
[PolyphaseCircuit](PolyphaseCircuit.html) specified by `winding_spec.circuit`  property.

Call syntax:

[] = create_slot_geometry(this, parent_geometry, winding_spec,
slot_or_surfaces), where

* parent_geometry : a [GeoBase](GeoBase.html) object

* winding_spec : a [PolyphaseWindingSpec](PolyphaseWindingSpec.html) object.

* slot : [SlotShape](SlotShape.html) object, or an array of [Surface](Surface.html)s in which case a
[SlotShapeWrapper](SlotShapeWrapper.html) object is created.

Depending on the winding model, this method calls
either the create_stranded_geometry or create_solid_geometry
methods. Custom cases must be subclassed.

### * create_solid_geometry Create slot geometry for solid winding
models.

### * create_stranded_geometry Finalize slot geometry of stranded windings.

### * gross_conductor_area Conductor area WITH insulation.

Returns the gross conductor area: useful area plus
insulation, per single conductor. Returns nan by default,
should be subclassed.

### * parse_slot_data Parse slot area, liner/insulation lengths.

### * uninsulated_winding_area Winding window area minus liners.

