---
title : SpaceVectors
parent: API
grand_parent : Documentation
---
## Summary
SpaceVectors Class for handling generalized Park-Clarke and inverse
transformations, almost following the methodology in
'A generalized transformation methodology for polyphase electric
machines and networks',  10.1109/IEMDC.2015.7409032.
## PROPERTIES
## Methods
Class methods are listed below. Inherited methods are not included.
### * Cmatrix Matrix for transforming to the alpha-beta frame.

C = ParkClarke.Cmatrix()

C = ParkClarke.Cmatrix(phases)

Matrix for transforming phase quantities to the non-rotating alpha-beta
frame. In this frame, the first 2 component correspond to the
traditional ab-frame. The next two components represent the third
harmonic, the next two the fifth, and so on. For odd phase numbers, the
last component is the zero-sequence component.

### * SpaceVectors.Pmatrix is a function.
P = Pmatrix(varargin)

### * SpaceVectors Class for handling generalized Park-Clarke and inverse
transformations, almost following the methodology in
'A generalized transformation methodology for polyphase electric
machines and networks',  10.1109/IEMDC.2015.7409032.

### * SpaceVectors.derivate_phase_values is a function.
dv = derivate_phase_values(x, angles, ts, varargin)

### * dq Transformation from phase quantities to the synchronous frame.

v = ParkClarke.dq(x, angles)

Transform phase quantities to the frames rotating at 1x (components
1-2), 3x (components 3-4), 5x (components 5-6) the frame defined by
input angles.

v = ParkClarke.dq(x, angles, bias)

Apply additional rotation, in total angles + bias.

v = ParkClarke.dq(x, angles, obj)

Parse bias angle from obj, being either a

* [MagneticsProblem](MagneticsProblem.html) object.

* [MotorModel](MotorModel.html) object.

### * xy Transformation from dq frame to synchronous frame (non-rotor
coordinates).

v = ParkClarke.xy(x, angles)

Transform phase quantities to the frames rotating at 1x (components
1-2), 3x (components 3-4), 5x (components 5-6) the frame defined by
input angles.

v = ParkClarke.xy(x, angles, bias)

Apply additional rotation, in total angles + bias.

v = ParkClarke.xy(x, angles, obj)

Parse bias angle from obj, being either a

* [MagneticsProblem](MagneticsProblem.html) object.

* [MotorModel](MotorModel.html) object.

### * inverse_transform Transform alpha-beta frame signal to phase quantities.

v = inverse_transform(x)

See ParkClarke.Cmatrix for details on the transformation.

### * TODO split 4-multiple-phase angles more evenly

### * transform Transform phase signal to the alpha-beta frame.

v = transform(x)

See ParkClarke.Cmatrix for details on the transformation.

### * SpaceVectors.uvectors is a function.
u = uvectors(varargin)

### * xy Transformation from synchronous frame to phase quantities.

v = ParkClarke.xy(x, angles)

Transform phase quantities to the frames rotating at 1x (components
1-2), 3x (components 3-4), 5x (components 5-6) the frame defined by
input angles.

v = ParkClarke.xy(x, angles, bias)

Apply additional rotation, in total angles + bias.

v = ParkClarke.xy(x, angles, obj)

Parse bias angle from obj, being either a

* [MagneticsProblem](MagneticsProblem.html) object.

* [MotorModel](MotorModel.html) object.

