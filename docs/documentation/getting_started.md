---
layout: default
title: Getting started
nav_order: 1
parent: Documentation
---

# Quick start guide

## First-time initialization instructions

1. Contact support (antti (at) smeklab.com) to obtain your [licence](../pricing.html) and download instruction.

1. Download and unzip the toolbox

1. Add EMDtool (with all subfolders) to your Matlab path
	- e.g. `addpath(genpath('C:/path_to_folder/EMDtool'))`
	- or add permanently via `startup.m`
  
1. Activate your license
  - `emdtool.load_license('license_file_name.lic')`

1. **(OPTIONAL:)(But preferred)** Download and unzip the free `gmsh` mesh generator for your operating system
    * [Downloads page](https://gmsh.info/#Download)
	* Please do recognize that `gmsh` is a separate software, governed by its own license agreement, only interfaced by `EMDtool` via a limited-functionality file interfaced
	* If you require other mesh generators, or wish to use `EMDtool`'s own development-version mesh generator, please enquire via email
	
1. **(OPTIONAL:)** Setup gmsh path, e.g. `emdtool.set_gmsh_path('C:/Programs/gmsh/')`
	- see `help emdtool.set_gmsh_path`
	
## Usage instructions

1. Add EMDtool to your Matlab path (see 3. above)
1. Analyze away!
	- see `Examples/readme.m` + example scripts for more detailed examples
	- or, see [EMDtool briefly](emdtool_briefly.html) for a brief overview

## Downloading a new version?

1. Download
  
1. Unzip

1. Add the new version to the path.

Indeed, you can easily switch between versions by simply adding and
removing versions from the Matlab path. It's a good idea to call `restoredefaultpath` and `clear classes` inbetween, though.

Occasionally, `Matlab` can be very obstinate about using old implementations of some classes, even if they have been nominally removed from the path. This can be verified by typing
`open <ClassName>` in the command window, to open the class file (or its docfile, in case of .p-files) in the editor, and then checking if its path is `old_version/EMDtool/ClassName.m` instead
of `new_version/EMDtool/ClassName.m`. Fear not - this is nothing that a good o' restart (of Matlab) won't fix.


