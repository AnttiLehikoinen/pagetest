---
title : Indexable
parent: API
grand_parent : Documentation
---
## Summary
Indexable is a class.
## PROPERTIES
* Indexable/dimensions is a property.

* Indexable/name is a property.

* Indexable/parent is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * Indexable/Indexable is a constructor.

### * == (EQ)   Test handle equality.
Handles are equal if they are handles for the same object.

H1 == H2 performs element-wise comparisons between handle arrays H1 and
H2.  H1 and H2 must be of the same dimensions unless one is a scalar.
The result is a logical array of the same dimensions, where each
element is an element-wise equality result.

If one of H1 or H2 is scalar, scalar expansion is performed and the
result will match the dimensions of the array that is not scalar.

TF = EQ(H1, H2) stores the result in a logical array of the same
dimensions.

See also INDEXABLE, INDEXABLE/GE, INDEXABLE/GT, INDEXABLE/LE, INDEXABLE/LT, INDEXABLE/NE
Help for Indexable/eq is inherited from superclass HANDLE

### * get Find an Indexable object by name.

obj = get(this, name)

### * get_dimension Get dimensions by name.

### * is_dimension Check if dimension exists.

### * ~= (NE)   Not equal relation for handles.
Handles are equal if they are handles for the same object and are
unequal otherwise.

H1 ~= H2 performs element-wise comparisons between handle arrays H1
and H2.  H1 and H2 must be of the same dimensions unless one is a
scalar.  The result is a logical array of the same dimensions, where
each element is an element-wise equality result.

If one of H1 or H2 is scalar, scalar expansion is performed and the
result will match the dimensions of the array that is not scalar.

TF = NE(H1, H2) stores the result in a logical array of the same
dimensions.

See also INDEXABLE, INDEXABLE/EQ, INDEXABLE/GE, INDEXABLE/GT, INDEXABLE/LE, INDEXABLE/LT
Help for Indexable/ne is inherited from superclass HANDLE

### * root Root parent.

### * Indexable/root_mesh is a function.
msh = root_mesh(this)

