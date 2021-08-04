---
layout: default
title: EMDtool
nav_order: 1
---

# EMDtool briefly

EMDtool is an Electric Motor Design toolbox for Matlab. It features full-functionality 2D Finite Element Analysis with nonlinearity, circuit connections, and motion, with under-development 3D capacity as well.

EMDtool is generally regarded as _fast_ compared to e.g. [FEMM](https://www.femm.info/wiki/HomePage) or Maxwell.

Finally, the [industrial licenses](pricing.html) of EMDtool are largely [source-available](https://en.wikipedia.org/wiki/Source-available_software), making it easy for you to extend and modify it to your organization's needs. This 
makes EMDtool the **ideal choice for medium-sized enterprises** that would greatly benefit from a custom-inhouse software toolkit, but don't have the resources to dedicate an entire team (or department) to building and 
maintaining one.

# History

EMDtool is loosely based on the open-source [SMEKlib library](https://github.com/AnttiLehikoinen/SMEKlib) developed at Aalto University, Finland, between 2013 and 2018 or so. This library was initially built out of
necessity - the Research Group of Electromechanics was (and still is) working on advanced loss model development, and commercial softwares were definitely not flexible enough for that purpose.

# Who is EMDtool for?

Coming soon
{: .label .label-yellow }

# Requirements

The main system requirements are listed below:

* A relatively recent version of Matlab
    * No additional Matlab toolboxes required
	
# Features

EMDtool is continuously developed. At the time of writing, the situation is as follows:

Existing features:

* Time-static and transient analysis in 2D, with motion.
* Class-based geometry definition
* Flexible definition of circuits, including
    * Polyphase circuits with current density, net current, or voltage supply
    * Large solid conductors like rotor bars or solid shafts
    * Axially-segmented solid conductors like permanent magnets 
* Simple post-processing of quantities of interest, including
    * Torque, current, and voltage waveforms
    * Visualization of flux and eddy-current densities
    * Losses 
* Synchronous machine analysis with current supply (sinusoidal & PWM):
    * Efficiency maps
    * Equivalent circuits
    * Automatic operation point iteration (current d- and q-axis components for reaching desired speed, torque point) 
	* Electrically-excited synchronous machines ([see example](https://www.anttilehikoinen.fi/general/mahle-magnet-free-motor-first-impressions/)) _under development_

Features under development; working but not pretty:
* 3D analysis, static and transient
    * Linear and nonlinear
	* Rotation/motion almost working
* Thermal analysis
* Rotor centrifugal stress analysis
* Different modulators
	* SVPWM and SHE at the moment

# Use cases

Coming soon
{: .label .label-yellow }