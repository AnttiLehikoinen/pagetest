---
title : SlotShapeBase
parent: API
grand_parent : Documentation
---
## Summary
SlotShapeBase Base class for slot shapes.

Like it's cousin [WindingLayoutBase](WindingLayoutBase.html), a `SlotShapeBase`  class is
intended to maximize reusability of custom code. Say you want to
implement a slot with a rectangular slot wedge, and fully non-rounded
slot-bottom corners, **and**  you want to use the same shape with two
different [StatorBase](StatorBase.html) stator templates. With a `SlotShapeBase`
subclass, you can.

The intended functionality is as follows. The `SlotShapeBase`  object
class creates all the [Surface](Surface.html)s associated with the slot: typically
the slot-opening (and wedge if any) and the winding layer(s).
Furthermore, it creates the [Material](Material.html) and [Domain](Domain.html) objects required
for the slot opening. All of the above is added to the parent
geometry (e.g. [Stator](Stator.html)).

The parent geometry is then only responsible for handling everything
outside the slot. To handle the airgap-facing part of the slot
opening, the class contains the property `airgap_surface_curves`  and
the methods `first_airgap_point`  and `last_airgap_point` , assuming
counter-clockwise orientation in everything.

Typically then, a `Surface`  would be created for the stator core.
And, as the slot and the core share a part of the airgap boundary,
the `reduce`  method of the core `Surface`  would then be called to
remove the slot surfaces of the core.

NOTE: It is assumed that no [Domain](Domain.html)s are created for the winding
`Surfaces` . By contrast, these are listed in the
`winding_window_surfaces`  property. Normally, the `SlotShapeBase`
object would then by passed on to a `WindingLayoutBase`  class, to
handle everything that goes on inside the winding window(s).

NOTE: For now, slot shapes generally work for stators only.
## PROPERTIES
* airgap_surface_curves - curves on the airgap surface, oriented ccw

* SlotShapeBase/interlayer_curves is a property.

* SlotShapeBase/liner_curves is a property.

* SlotShapeBase/parent_geometry is a property.

* SlotShapeBase/winding_window_area is a property.

* SlotShapeBase/winding_window_surfaces is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SlotShapeBase Base class for slot shapes.

Like it's cousin [WindingLayoutBase](WindingLayoutBase.html), a `SlotShapeBase`  class is
intended to maximize reusability of custom code. Say you want to
implement a slot with a rectangular slot wedge, and fully non-rounded
slot-bottom corners, **and**  you want to use the same shape with two
different [StatorBase](StatorBase.html) stator templates. With a `SlotShapeBase`
subclass, you can.

The intended functionality is as follows. The `SlotShapeBase`  object
class creates all the [Surface](Surface.html)s associated with the slot: typically
the slot-opening (and wedge if any) and the winding layer(s).
Furthermore, it creates the [Material](Material.html) and [Domain](Domain.html) objects required
for the slot opening. All of the above is added to the parent
geometry (e.g. [Stator](Stator.html)).

The parent geometry is then only responsible for handling everything
outside the slot. To handle the airgap-facing part of the slot
opening, the class contains the property `airgap_surface_curves`  and
the methods `first_airgap_point`  and `last_airgap_point` , assuming
counter-clockwise orientation in everything.

Typically then, a `Surface`  would be created for the stator core.
And, as the slot and the core share a part of the airgap boundary,
the `reduce`  method of the core `Surface`  would then be called to
remove the slot surfaces of the core.

NOTE: It is assumed that no [Domain](Domain.html)s are created for the winding
`Surfaces` . By contrast, these are listed in the
`winding_window_surfaces`  property. Normally, the `SlotShapeBase`
object would then by passed on to a `WindingLayoutBase`  class, to
handle everything that goes on inside the winding window(s).

NOTE: For now, slot shapes generally work for stators only.

### * SlotShapeBase/create_geometry is a function.

### * SlotShapeBase/first_airgap_point is a function.
P = first_airgap_point(this)

### * initialize Parse characteristic lengths and initialize
dimensions.

### * SlotShapeBase/last_airgap_point is a function.
P = last_airgap_point(this)

### * orientation_angle Angle of principal-like axis of this.surfaces.

Typically: angular coordinate of first slot of parent geometry.

### * determining lines

### * SlotShapeBase/set_parent is a function.
set_parent(this, parent)

### * free_height_of_surface Free height of surface.

h = free_height_of_surface(this, k_surface)

