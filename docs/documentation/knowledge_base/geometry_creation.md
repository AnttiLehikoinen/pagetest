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

## Creating materials

Materials are objects, and subclasses of the `MaterialBase` class. Most importantly, they contain the functionality required for modelling
the (generally non-linear) B-H relationship of the material in question.

The majority of the time, your materials will be of the simple anisotropic, non-hysteretic `Material` class, and created using one of the 
following methods:

* Using the `Material.create(0)` method to use one of the early `EMDtool` built-in materials. In the example before, the index 0 would
be for air, folks

* Using the `PMlibrary.create` or `SteelLibrary.create` methods, to gain access to more, newer, and more regularly-updated materials.

* Use your own materials, most often wrapped inside a function calling the `Material.from_specs` method.


# Case Example: Solid Rotor for a High-Speed Induction Motor
