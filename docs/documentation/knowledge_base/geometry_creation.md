---
layout: default
title: Geometry Creation
parent: Knowledge Base
grand_parent : Documentation
math: mathjax2
---

# Creating your own geometries

So, how to create your own geometries? Read here to learn, or at least get started.

# Model hierarchy

Before anything else, let's rehash how analysis with `EMDtool` works. Like we saw in the [EMDtool briefly](../emdtool_briefly) page, we obtain results by first solving a [`problem`](../../api/MagneticsProblem.html)
object.

The `problem`, just before ~~has eaten~~ is associated with a `Model`. 95 % of the time, it is an [RFmodel](../../api/RFmodel.html), containing as `components` a _stator_ and a _rotor_. The model has
a few additional responsibilities, like

* Returning an airgap matrix for modelling rotation. You may have to overwrite this method to study e.g. magnetic gears or other systems where you have two or more components rotating at different speeds.

* Returning some properties for the components. For example, the stator and rotor typically are at different temperatures, and see a different frequency in harmonic analysis.

Anyways, this now brings us to the components, for example the `stator`. Each component is a subclass of the [`GeoBase`](../../api/GeoBase.html) class, typically called a **template**. 
To create your own custom geometries, templates are what you have to work with.

# Geometry components

Geometry components - subclasses of the [`GeoBase`](../../api/GeoBase.html) class - each describe one "independent" component of the problem geometry - think a stator and a rotor.

Each component contains all the information required to describe it (in analysis-terms at least), in the corresponding `properties`:

* `.mesh` : a mesh object, containing the finite element mesh elements and nodes

* `.domains` : [Domains](../../api/Domain.html) of the component, each corresponding to an interesting part of the component, like for example the stator core. Each Domain then contains at least:

	* The [Material](../../api/MaterialBase.html) it is made of.
	
	* The elements that belong to it.
	
* `.materials` : all [Materials](../../api/MaterialBase.html) that are present in the component.

* `.circuits` : all [Circuits](../../api/CircuitBase.html) in the component, if any.

Finally, what turns a mere component into a template is the fact that it is **parametric**. This means that each template class implements the `.create_geometry` method. This method takes as an input a
`structure` of dimensions, and uses the information to create the Domains, Materials, Circuits, and enough information to allow automatic mesh generation with the `.mesh_geometry` method. More of this next.

# Creating a geometry template

Like implied above, you can create geometry template class by subclassing the [GeoBase](../../api/GeoBase.html) class, and then implementing the `.create_geometry` method.

**Note:** in practice, you will in fact be subclassing another subclass such as [StatorBase](../../api/StatorBase.html), [SlottedRotorBase](../../api/SlottedRotorBase.html), or
[SynRotorBase](../../api/SynRotorBase.html). This is because many of the finer analysis features require some other methods from the templates. An example is the `.d_axis_angle` for rotor templates, to
allow automatic dq-transformations.

Most likely, you will implement the `.create_geometry` method in its own separate file. Inside the file, you will generally do the following 
steps:

1. Create the `Material`s used in the model, and add them to the component.

1. Create the `Domain`s used and add them to the component.

1. Create the `Circuit`s used, and add them to the component.

Now, let's take a brief look at each of these steps.

## Creating Materials

Materials are objects, and subclasses of the `MaterialBase` class. Most importantly, they contain the functionality required for modelling
the (generally non-linear) B-H relationship of the material in question.

The majority of the time, your materials will be of the simple anisotropic, non-hysteretic `Material` class, and created using one of the 
following methods:

* Using the `Material.create(0)` method to use one of the early `EMDtool` built-in materials. In the example before, the index 0 would
be for air, folks

* Using the `PMlibrary.create` or `SteelLibrary.create` methods, to gain access to more, newer, and more regularly-updated materials.

* Use your own materials, most often wrapped inside a function calling the `Material.from_specs` method.


After creation, the material objects are added to your component with `this.add_material( material_object )`. Here `this` of
course refers to your template object, like `this` in Java or `self` in Python). For some reason, the Matlab documentation uses `obj` 
instead.

## Creating Domains

Domains are also objects, each consisting of a single material (at least for the foreseeable future), and representing one interesting part
of the geometry. For instance, one bar of an induction motor would normally by a `Domain`, as would the part of the stator core within one slot
pitch.

Domains themselves are very easy to define. However, for them to actually mean anything, you will have to add one or more `Surfaces` to each
of them, to tell `EMDtool` something about the actual geometry. We will take a closer look on this later.

For now, the code snippet below demonstrates the usage of `Domains` in a simple form.

```matlab
core_domain = Domain('Rotor_core', core_material);
core_domain.add_surface(core_surface);
this.add_domain(core_domain);
```

## Creating Circuits

Although optional, `Circuits` do feature as a part of most geometry templates. After all, motors typically have windings where currents
should flow, and other conductive bodies where they should not but still do (eddy currents).

An example tells more than a thousand words, so here is one:

````matlab
core_circuit = SheetCircuit('Rotor_core');
core_conductor = SolidConductor(core_domain);
core_circuit.add_conductor(core_conductor);
this.add_circuit(core_circuit);
```

In this example, we are presumably dealing with a high-speed induction motor with a solid core. To model the eddy-currents induced
into the core, we have to create a `CircuitBase` object for it.

Specifically, we will create a `SheetCircuit` object. A sheet circuit is a special kind of circuit, reserved for solid bodies that
span the entire circumference of a motor. Think a cylindrical copper shell (a sheet) used as an eddy current shield, a solid shaft, a
solid frame, or indeed a solid core.

**Note:** Were we modelling the entire cross section of the machine, there would be nothing special about a sheet circuit. However,
the assumption in `EMDtool` is that we are only modelling one symmetry sector. Say we have a conducting body in the symmetry sector, and
by extension a similar body in all the other (non-modelled) sectors. In reality, the sector-bodies may form a single continuous body
(like a shaft or our rotor core in the example), or they may be separate from each other (like a PM segment inside an IPM rotor). The
former case would call for a `SheetCircuit`, whereas for the latter a `BlockCircuit` or perhaps an `ExtrudedBlockCircuit` would be more
appropriate.

Back to the example: after creating the circuit, we create a `SolidConductor` object to wrap the `Core` `Domain` created earlier. Then,
this conductor is added to the circuit, and the circuit is added to the geometry template itself.


# Case Example: Solid Rotor for a High-Speed Induction Motor

Next, let's take a look at a very simple yet complete-ish template example. The template in question is for a very simple high-speed 
induction motor rotor: no slits, no coats, no shaft.

The template is located inside a folder called `@SimpleSolidRotor`, with the @-sign telling Matlab that a folder defines a class.

Inside the folder, the first file is the main class definition file `SimpleSolidRotor.m`. Its entire contents are listed below:

```matlab
classdef SimpleSolidRotor < SynRotorBase
    methods
        create_geometry(this)
    end
end
```

So, the class inherits the `SynRotorBase` class. Even though not _synchronous_, inheriting this class saves us some trouble of implementing
some other functionality needed (see the `RadialGeometry` class for a list).

Furthermore, the class file tells Matlab that the main geometry creation function `create_geometry` in inside a different file. Let's
take a look at it next.

The first few lines of the `create_geometry.m` file read

```matlab
dim = this.dimensions;
Rout = dim.Rout; %outer radius
angle_pole = pi / dim.p; %pole angle
lcar_ag = Airgap.characteristic_length(this);
lcar_center = Rout/5;
```

What happens here is that we extract the dimensions `structure` given as input to the class constructor, and then save the radius of 
the rotor along with its pole pitch (in radians) to internal variables `Rout` and `angle_pole`.

Finally, we compute some _characteristic lengths_ to control the mesh density on the airgap surface and the rotor center, respectively.

Next, we repeat the steps we already saw earlier, initializing the Materials, Domains, and Circuits needed for the model.

```matlab
core_material = Material.create( dim.rotor_core_material );
this.add_material(core_material);

core_domain = Domain('Rotor_core', core_material);
this.add_domain(core_domain);

core_circuit = SheetCircuit('Rotor_core');
core_conductor = SolidConductor(core_domain);
core_circuit.add_conductor(core_conductor);
this.add_circuit(core_circuit);
```
Next, we repeat the steps we already saw earlier, initializing the Materials, Domains, and Circuits needed for the model.