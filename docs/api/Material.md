---
title : Material
parent: API
grand_parent : Documentation
---
## Summary
Material Basic isotropic material class.

Materials are normally instantiated with the static methods

* |Material.create|

* |Material.from_specs|
## PROPERTIES
* B - given B-curve

* Material/BH_extrapolation_method is a property.

* H - given H-curve

* Material/data is a property.

* domains - list of **domains** that are made of this material

* elements - indices to finite elements

* is_symmetric - Is the differential reluctivity symmetric?

* material_properties - struct of material properties

* plot_args - plotting instructions for this

* stacking_factors - list of stacking factors per each element

## Methods
Class methods are listed below. Inherited methods are not included.
### * harmonic-approximation BH-curve (eq. (47) in Arkkio's thesis)

### * Material/add_domain is a function.
this = add_domain(this, domain)

### * clear_copy New independent copy of the material.

### * create Create material

mat = Material.create(material_object)

Return a clear_copy of material_object.

mat = Material.create(matid)

Create a material from library, see get_defaultMaterial

mat = Material.create()

Create an empty Material object.

### * initialize_material_data Calculate reluctivities etc.

Compute reluctivities and extrapolate BH data.

Reluctivity data as a function of B^2 is saved to |this.data|.

### * detach Clear elements, domains, etc.

### * differential_reluctivity Return reluctivity and its derivative.

[nu, dnu] = differential_reluctivity(this, Bvector, true)

Return reluctivity and its derivative w.r.t. |B|^2 computed with the
harmonic approximation

[H, dHdB] = differential_reluctivity(this, Bvector)

Return magnetic field strength vector and the differential reluctivity
tensor. Only works in 2D.

### * extrapolate_BH_langevin Extrapolate BH data with constant magnetization.

[Bext, Hext] = extrapolate_BH_langevin(B, H) extrapolate given BH data by
assuming a constant magnetization beyond the given range.

Returns original BH data appended by extrapolated data.

### * extrapolate_BH_data Extrapolate given BH data.

[Bext, Hext]  = extrapolate_BH_data(this, B, H) extrapolate BH data with
the method specified in this.BH_extrapolation_method:

* 'langevin' : fitting a single Langevin function to the data, using
Material.extrapolate_BH_langevin

* 'constant' : extrapolate using constant magnetization equal to the
last datapoint in the given BH data. Uses Material.extrapolate_BH_constant

* 'linear' : linear extrapolation of BH curve. Uses Material.extrapolate_BH_linear

* for other approaches, please subclass Material.

Returns original BH data appended by extrapolated data.

### * extrapolate_BH_langevin Extrapolate BH data with Langevin approach.

[Bext, Hext] = extrapolate_BH_langevin(B, H) extrapolate given BH data by
fitting the single-valued Langevin function to the data; specifically by
matching the value and slope at the end of the given BH curve.

Returns original BH data appended by extrapolated data.

### * extrapolate_BH_linear Extrapolate BH data with linear extrapolation.


Returns original BH data appended by extrapolated data.

### * fit_Langevin1 Process BH data with Langevin approach.

fit_Langevin1(this)

Process given BH data (this.B, this.H). Given data range is used as
such. Extrapolation to higher flux densities is performed by fitting
the single Langevin function to the data, and using it for
extrapolation.

fit_Langevin1(this, 'monotonicity_factor', c)

Additional improve the reluctivity-monotonicity of the given data with
the following approach:

1. Compute nu = H / B

2. Make nu monotonic.

3. Compute H_monotonic = nu * B

4. Replace H := (1-c)*H_original + c*H_monotonic.

5. Proceeed as earlier.

Even a small monotonicity factor can often improve the convergence of
nonlinear problems.

NOTE: Original BH data is not modified.

### * from_specs Create material from specs.

Call syntax:

mat = Material.from_specs('name', name, 'B', B_curve_vector,
'H', H_curve_vector, 'property_name_1', value_1, ...)

### * init_for_problem Initialize object for problem.

Normally, this method does very little apart from determining the
stacking factors. It could be used to initialize hysteresis models or
similar in subclasses on Material, though.

### * initialize_material_data Initialize reluctivity curves etc.

initialize_material_data(this)

Process given BH data (this.B, this.H). Given data range is used as
such. Extrapolation to higher flux densities is performed by
this.extrapolate_BH_data

initialize_material_data(this, 'monotonicity_factor', c)

Additional improve the reluctivity-monotonicity of the given data with
the following approach:

1. Compute nu = H / B

2. Make nu monotonic.

3. Compute H_monotonic = nu * B

4. Replace H := (1-c)*H_original + c*H_monotonic.

5. Proceeed as earlier.

Even a small monotonicity factor can often improve the convergence of
nonlinear problems.

NOTE: Original BH data is not modified.

### * iron_loss_density_time_domain_Steinmetz Iron loss density from modified Steinmetz
model, in W/kg.

[physt, peddy] = ...
iron_loss_density_time_domain_Steinmetz(this, timestamps, Bx, By)

physt = hysteresis loss density = ch ** (|Bx^a ** dBx/dt^b| + |By^a * dBy/dt^b|

where a=b=1 by default, if not given in
this.material_properties.steinmetz_exponents = 1x2 vector

peddy = eddy loss density = ce * ( (dBx/dt)^2 + (dBy/dt)^2 )

### * plot_BH Plot BH curves etc.

### * Material.process_BH is a function.
[Bnu, Bdnu] = process_BH(BH, varargin)

### * raw_reluctivity Evaluate (non-differential) reluctivity.

nu = raw_reluctivity(this, B2)

### * save_to_excel Save material specs to Excel.

### * set_step Set new time-step.

set_step(this, kstep, t, varargin)

Does nothing by default

### * Material/shift_elements is a function.
this = shift_elements(this, Ne)

### * Material/thermal_conductivity is a function.
l = thermal_conductivity(this)

