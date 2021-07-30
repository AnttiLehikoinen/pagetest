---
title : SlotShapeBase
parent: API
grand_parent : Documentation
---
## Summary
SlotShapeBase methods:
SlotShapeBase - is a class.
parse_curves - determining lines
## PROPERTIES
* airgap_surface_curves - curves on the airgap surface, oriented ccw

* SlotShapeBase/interlayer_curves is a property.

* SlotShapeBase/liner_curves is a property.

* SlotShapeBase/parent_geometry is a property.

* SlotShapeBase/winding_window_area is a property.

* SlotShapeBase/winding_window_surfaces is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SlotShapeBase/SlotShapeBase is a constructor.
this = SlotShapeBase(parent)

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

