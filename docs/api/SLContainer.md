---
title : SLContainer
parent: API
grand_parent : Documentation
---
## Summary
SLContainer A SMEKlib container class for key-value pairs.

Has the following methods:

value = get(key); returns [] if not found.

set(key, value) (overwrites existing).

add(key, value) (append to existing; only for arrays).

keys() returns the keys.

copy() returns a deep copy.

(c) 2017 Antti Lehikoinen / Aalto University
## PROPERTIES
* SLContainer/data is a property.

## Methods
Class methods are listed below. Inherited methods are not included.
### * SLContainer A SMEKlib container class for key-value pairs.

Has the following methods:

value = get(key); returns [] if not found.

set(key, value) (overwrites existing).

add(key, value) (append to existing; only for arrays).

keys() returns the keys.

copy() returns a deep copy.

(c) 2017 Antti Lehikoinen / Aalto University

### * SLContainer/add is a function.
c = add(c, name, d)

### * SLContainer/copy is a function.
c2 = copy(c)

### * GET    Get object properties.
V = GET(H,'PropertyName') returns the value of the specified property
for the graphics object with handle H.  If H is a vector of handles,
then **get** will return an M-by-1 cell array of values where M is equal
to length(H).  If 'PropertyName' is replaced by a 1-by-N or N-by-1 cell
array of strings containing property names, then GET will return an
M-by-N cell array of values.

GET(H) displays the names and current values of all user-gettable
properties for the graphics object with handle H.

V = GET(H) where H is a scalar, returns a structure where each field
name is the name of a user-gettable property of H and each field
contains the value of that property.

V = GET(0, 'Factory')
V = GET(0, 'Factory[ObjectType](ObjectType.html)')
V = GET(0, 'Factory[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)')
returns for all object types the factory values of all properties
which have user-settable default values.

V = GET(H, 'Default')
V = GET(H, 'Default[ObjectType](ObjectType.html)')
V = GET(H, 'Default[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)')
returns information about default property values (H must be scalar).
'Default' returns a list of all default property values currently set
on H.  'Default[ObjectType](ObjectType.html)' returns only the defaults for properties
of [ObjectType](ObjectType.html) set on H.
'Default[ObjectType](ObjectType.html)[PropertyName](PropertyName.html)' returns the default value for the
specific property, by searching the defaults set on H and its
ancestors, until that default is found.  If no default value for this
property has been set on H or any ancestor of H up through the root,
then the factory value for that property is returned.

Defaults can not be queried on a descendant of the object, or on the
object itself - for example, a value for 'DefaultAxesColor' can not
be queried on an axes or an axes child, but can be queried on a figure
or on the root.

When using the 'Factory' or 'Default' GET, if PropertyName is omitted
then the return value will take the form of a structure in which each
field name is a property name and the corresponding value is the value
of that property.  If PropertyName is specified then a matrix or string
value will be returned.


See also SET, RESET, DELETE, GCF, GCA, FIGURE, AXES.

### * SLContainer/keys is a function.
names = keys(c)

### * SET    Set object properties.
SET(H,'PropertyName',PropertyValue) sets the value of the specified
property for the graphics object with handle H.  H can be a vector of
handles, in which case SET sets the properties' values for all objects
of H.

SET(H,a) where a is a structure whose field names are object property
names, sets the properties named in each field name with the values
contained in the structure.

SET(H,pn,pv) sets the named properties specified in the cell array of
strings pn to the corresponding values in the cell array pv for all
objects specified in H.  The cell array pn must be 1-by-N, but the cell
array pv can be M-by-N where M is equal to length(H) so that each
object will be updated with a different **set** of values for the list of
property names contained in pn.

SET(H,'PropertyName1',PropertyValue1,'PropertyName2',PropertyValue2,...)
sets multiple property values with a single statement.  Note that it
is permissible to use property/value string pairs, structures, and
property/value cell array pairs in the same call to SET.

A = SET(H, 'PropertyName')
SET(H,'PropertyName')
returns or displays the possible values for the specified property of
the object with handle H.  The returned array is a cell array of
possible value strings or an empty cell array if the property does not
have a finite **set** of possible string values.

A = SET(H)
SET(H)
returns or displays the names of the user-settable properties and
their possible values for the object with handle H.  The return value
is a structure whose field names are the user-settable property names
of H, and whose values are cell arrays of possible property values or
empty cell arrays.

The default value for an object property can be **set** on any of an
object's ancestors by setting the PropertyName formed by concatenating
the string 'Default', the object type, and the property name.  For
example, to **set** the default color of text objects to red in the current
figure window:

set(gcf,'DefaultTextColor','red')

Defaults can not be **set** on a descendant of the object, or on the
object itself - for example, a value for 'DefaultAxesColor' can not
be **set** on an axes or an axes child, but can be **set** on a figure or on
the root.

Three strings have special meaning for PropertyValues:
'default' - use default value (from nearest ancestor)
'factory' - use factory default value
'remove'  - remove default value.

See also GET, RESET, DELETE, GCF, GCA, FIGURE, AXES.

