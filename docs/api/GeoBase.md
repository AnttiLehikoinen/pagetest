---
title : GeoBase
parent: API
grand_parent : Documentation
---
## Summary
GeoBase Base class for geometries.

Basic usage:

* Add some [Domain](Domain.html)s with `this.add_domain`

* Add the <Material.html required Materials> with `this.add_material`

* Optionally, add some <CircuitBase.html Circuits> with
`this.add_circuit`

* Call `this.mesh_geometry`  to mesh the elementary geometry and
replicate accordingly.

Note that his is an abstract base class and cannot be instantiated.
Most of the time, you'll be working with either RadialGeometry or AxialGeometry,
or their subclasses. Those classes
handle the practicalities of mesh replication, namely how the
elementary mesh is rotated or translated.

The following methods are recommended to be re-implemented in
subclasses:

* Nrep : number of mesh replications

* symmetry_period : symmetry period of winding etc.

See [RadialGeometry](RadialGeometry.html), [StatorBase](StatorBase.html), [SlottedRotorBase](SlottedRotorBase.html),
[SynRotorBase](SynRotorBase.html)
## PROPERTIES
* PMs -  Permanent magnet [Domain](Domain.html) objects

* GeoBase/boundaries is a property.

* circuits -  [Circuit](Circuit.html) objects defined for this

* data - miscellaneous data

* domains -  [Domain](Domain.html) objects making up this

* nodes = struct() %other nodes

* GeoBase/is_meshed is a property.

* materials -  [Material](Material.html) objects

* mesh - **mesh** object, WPI

* n_ag - Airgap boundary nodes

* n_ccw - Counter-clockwise periodic boundary nodes

* n_cw - Clock-wise periodic boundary nodes

* n_dir - Dirichlet (flux insulation) boundary nodes

* p - Coordinates of nodes, 2xN array

* t - Element indices to this.nodes, nxN array

## Methods
Class methods are listed below. Inherited methods are not included.
### * GeoBase Constructor

### * Nrep Number of times to replicate elementary mesh.

Nrep(this)

Usually subclassed, but by default returns
this.dimensions.Nrep.

### * add_circuit Add [Circuit](Circuit.html) to this.

### * add_domain Add [Domain](Domain.html) to this.

### * add_material Add [Material](Material.html) to this.

### * GeoBase/check_feasibility is a function.
bl = check_feasibility(this, varargin)

### * copy_domain Copy domain and apply necessary rotations or
translations to the domain and remanence orientation, if any.

new = copy_domain(this, old_domain, sector_index)

### * create_or_get_material Create or get material.

mout = create_and_add_material(this, m) either

* returns a material mout from this.materials with mout.name = m.name

* returns m, if none found above, and adds it to this.materials

### * create_geometry Initialize geometry.

this = create_geometry(this, varargin)

Initializes the geometry.

Must be subclassed.

### * GeoBase/dim is a function.
d = dim(this)

### * export_dxf Export geometry as rudimentary dxf file.

export_dxf(this, fname)

drawing = export_dxf(this, fname, 'skip_save', true) to return drawing
object

export_dxf(this, drawing)

export_dxf(this, fname_or_drawing, key, val, ...) with

* 'Nrep', n : replicate geometry, see below

* 'rep_angle', x : apply angle x for each replication

* 'unit', 'm' or 'mm' : unit to use

* use_python : use Python's dxfwrite (true) or Matlab's dxflib with
experimental ARC and LINE features (DEFAULT).

### * fill Fill mesh

fill(this, name, varargin)

Fills the mesh of domain *name* , using varargin{:} as
arguments.

* See [msh_fill](msh_fill.html)
* See this.get_domain for the use of wildcards with *name*

fill(this, varargin)

Plots the entire mesh using varargin{:} as
arguments.

### * get_domain Get domain(s) by name.

get_domain(this, name)

Returns the [Domain](Domain.html) with the correct *name* .

The wildcard syntax name_* can be used to find all
replicated domains corresponding to the original domain
with *name* .

### * list_dimensions Display dimensions info on command window

### * GeoBase/mass is a function.
[m, m_domain, m_mat] = mass(this)

### * mesh_elementary_geometry Create mesh for the elementary geometry.

mesh_elementary_geometry(this)

Meshes the *elementary*  geometry, e.g. the raw geometry before possible
replication.

Note that the methods `this.shift_elementary_nodes` ,
`this.copy_domain` , and `this.parse_nodes`  have to be implemented.

### * GeoBase/mesh_elementary_geometry_3D is a function.
mesh_elementary_geometry_3D(this, varargin)

### * mesh_geometry Mesh geometry.

Equivalent to calling `this.mesh_elementary_geometry`  and
`this.replicate_elementary_mesh`

### * parse_nodes Parse special nodes.

parse_nodes(this, Surfaces)

Parses special nodes from meshed Surfaces. Usually airgap
and periodic boundary nodes.

### * plot Plot nodes on the meshed geometry.

plot(this, varargin)

Equivalent to calling msh_plot(this, varargin{:})

### * plot_edges Plot edges

### * plot_geometry Plots the geometry.

[] = plot_geometry(this, varargin)

Plots the geometry using *plot*  with *varargin* {:}

### * replicate_elementary_mesh Replicate elementary mesh.

replicate_elementary_mesh(this, sector_shift, Nrep)

Replicates the elementary geometry *Nrep*  times. This is performed by

* applying the sector_shift to this.p, using this.shift_elementary_nodes

* eliminating the duplicate nodes on the inter-sector boundaries, with
the nodes corresponding to this.n_cw replaced by this.n_ccw.

### * GeoBase/replicate_elementary_mesh_3D is a function.
replicate_elementary_mesh_3D(this)

### * save_to_excel Save specifications to Excel sheet.

save_to_excel(this, fname, varargin)

### * shift_elementary_nodes Replicate nodes to a new sector.

pnew = shift_elementary_nodes(this, p, k)

Replicated the nodes p of the elementary symmetry sector into
the sector k.

### * symmetry_period Symmetry period of the geometry.

symmetry_period(this)

Usually subclassed, but by default returns
this.dimensions.symmetry_period.

### * triplot Triangle plot of this.

triplot(this, name, varargin)

Plots the mesh of domain *name* , using varargin{:} as
arguments.

triplot(this, varargin)

Plots the entire mesh using varargin{:} as
arguments.

### * visualize **visualize** geometry.

visualize(this)

Visualizes geometry, using msh_fill with 'linestyle',
'none'.

visualize(this, args)

Visualize, passing args to patch.

