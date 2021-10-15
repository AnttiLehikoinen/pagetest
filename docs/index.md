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

Please send an email to antti (at) smeklab.com to enquire about a [license](pricing.html).

# How does EMDtool work?

Please check the [getting started guide](documentation/getting_started.html) and the [`EMDtool` overview](documentation/emdtool_briefly.html) to get a quick first impression.

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

# Frequently-asked questions

For questions on the toolbox itself, please first refer to the [documentation](documentation/documentation.html). Other common questions are listed below.

### Is there support?

Yes. Time for honesty here - only a small number of `EMDtool` licenses have been sold so far. That means quite personalized support.

### Can **Feature X** be added?

Most likely yes. If it's something small, that's [on the house](https://www.smeklab.com).

Something bigger would then call for a joint development project. Normally, that would work as a consulting-style arrangement, at break-even price, with the new functionality added to the future `EMDtool`
releases (apart from possible minor confidential parts such as custom geometry templates).

### Does EMDtool work with Octave/Scilab?

No, unfortunately. Octave does claim compatibility with Matlab, but this claim does not seem to be correct. For instance, object arrays are not supported.

### Is there a Python version?

That'd again be a no. A Python implementation would be lovely, but porting the existing codebase would be quite a formidable task. 

Futhermore, Matlab's JIT (just-in-time) compiler is pretty much the best on market, resulting in very fast execution. Python does have `Numba`, which unfortunately only works on rather elementary operations.
By contrast, a huge majority of the lines-of-code in `EMDtool` cannot be easily translated to low-lever format.
