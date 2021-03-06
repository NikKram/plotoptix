Release history
===============

`v0.5.2`_ - 2019-10-15
----------------------

Fixed
~~~~~

- dependency on vcruntime140_1.dll in Windows binaries, introduced in v0.5.1 with the VS tools upgrade 

`v0.5.1`_ - 2019-09-27
----------------------

Added
~~~~~

- ray tracing timeout parameter, use set_param(rt_timeout=n_ms) and get_param("rt_timeout")

Fixed
~~~~~

- timeout instead of freeze if stucked in the internal OptiX launch() function
- default lighting was not initialized properly after refactoring made in v0.5.0

`v0.5.0`_ - 2019-09-20
----------------------

Added
~~~~~

- scene saving/loading in JSON file format or python's dictionary (note, format is not finally freezed and may
  change on migration to OptiX 7)
- callbacks re-configurable after initialization
- load selected/all/merged objects from Wavefront .obj files
- thin-walled material

Changes
~~~~~~~

- load_mesh_obj() method renamed to load_merged_mesh_obj(); the new load_mesh_obj() loads meshes selected by
  the name or loads all meshes from the file with no merging
- light shading mode configured with set_param() and get_param() methods

`v0.4.8`_ - 2019-09-07
----------------------

Added
~~~~~

- Oren-Nayar diffuse reflectance model (in addition to the default Lambertian), adjustable surface roughness
- adjustable surface rougness also for metalic and dielectric (glass) materials, improved predefined materials

Changes
~~~~~~~

- metalic and mirror materials use primitive colors to colorize the reflection (primitive color overrides
  surface albedo) so color data can be effectively used also with these materials

`v0.4.7`_ - 2019-08-28
----------------------

Added
~~~~~

- select and rotate/move/scale objects and lights in GUI with mouse (same as for the camera)
- status bar in GUI, shows selected item, 2D/3D coordinates of the surface under the pointer, and FPS
- method to set fixed size of the ray-tracing output in GUI (or go back to auto-fit to window size)

`v0.4.6`_ - 2019-08-19
----------------------

Added
~~~~~

- methods to rotate camera about given point, eye about target, target about eye, in local and global coordinates

Changes
~~~~~~~

- calculate normal tilt on the fly in the surface displacement mode, speed not affected, much lower gpu memory footprint

Fixed
~~~~~

- normal tilt mode in textured parallelepipeds bug resulting with transparent walls in some configs

`v0.4.5`_ - 2019-08-11
----------------------

Added
~~~~~

- particles geometry with 3D orientation (so textures can be applied), textured glass color
- shading normal tilt (particles, parallelograms, parellelepipeds, tetrahedrons) and surface displacement (particles) using texture data
- overlay a texture in 2D postprocessing

`v0.4.2`_ - 2019-07-23
----------------------

Added
~~~~~

- method to get light source parameters in a dictionary
- examples installer - so examples compatible with the recent PyPI release can be downloaded locally without cloning the repository

Fixed
~~~~~

- OptiX-CUDA interop: readback buffer pointer is now obtained for a single GPU in multi-GPU systems, this solves issue on multi-GPU systems

`v0.4.1`_ - 2019-07-14
----------------------

Added
~~~~~

- 2D color preprocessing utility
- reading normalized images

Fixed
~~~~~

- read_image method name in linux library loader

`v0.4.0`_ - 2019-07-06
----------------------

Added
~~~~~

- AI denoiser
- light dispersion in refractions
- method to update material properties after construction
- enable textured materials
- utilities for reading image files to numpy array, support for huge tiff images (>>GB)

Fixed
~~~~~

- update of parallelogram light properties
- selection of SM architecture

`v0.3.1`_ - 2019-06-26
----------------------

Added
~~~~~

- textured background (fixed texture or environment map, from numpy array or image file)
- json converters for vector types (more compact scene description)

Fixed
~~~~~

- removed dependency on CUDA release, CUDA required for video encoding features only

`v0.3.0`_ - 2019-06-09
----------------------

Added
~~~~~

- **linux support**
- parametric surface

Changes
~~~~~~~

- update to NVIDIA Video Codec SDK 9.0 and FFmpeg 4.1
- no need for CUDA_PATH environment variable

`v0.2.2`_ - 2019-05-26
----------------------

Added
~~~~~

- color calculation convenience method: scaling, exposure and inverted gamma correction
- h.264 encoder profile and preset selection

Changes
~~~~~~~

- major speed improvement in general, plus faser convergence in out of focus regions
- refactoring for linux support

Fixed
~~~~~

- missing parallelogram support

`v0.2.1`_ - 2019-05-19
----------------------

Added
~~~~~

- OpenSimplex noise generator
- basic interface to the video encoder (save video output to mp4 files)
- save current image to file

`v0.2.0`_ - 2019-05-12
----------------------

Added
~~~~~

- RTX-accelerated mesh geometry for surface plots, reading 3D meshes from Wavefront .obj fromat
- several configurable 2D postprocessing stages

Fixed
~~~~~

- bug on geometry update when data size was changed with u/v/w vectors not provided

`v0.1.4`_ - 2019-04-25
----------------------

Added
~~~~~

- methods to rotate geometry/primitive about provided 3D point
- autogenerated documentation, improved and completed docstring in the code

Changed
~~~~~~~

- use tuples instead of x, y, z arguments in rotation/move methods

`v0.1.3`_ - 2019-04-19
----------------------

Added
~~~~~

- RTX-accelerated tetrahedrons geometry
- generate aligned or randomly rotated data markers if some vectors are missing
- methods to read back camera eye/target, light position, color and r/u/v
- get_param() to read back the rt parameters
- this changelog, markdown description content type tag for PyPI
- use [Semantic Versioning](https://semver.org/spec/v2.0.0.html)

v0.1.2.5 - 2019-04-16
---------------------

Two weeks and some steps from the initial release. Starting changelog relative to this point.

.. _`v0.5.2`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.5.2
.. _`v0.5.1`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.5.1
.. _`v0.5.0`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.5.0
.. _`v0.4.8`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.8
.. _`v0.4.7`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.7
.. _`v0.4.6`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.6
.. _`v0.4.5`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.5
.. _`v0.4.2`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.2
.. _`v0.4.1`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.1
.. _`v0.4.0`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.4.0
.. _`v0.3.1`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.3.1
.. _`v0.3.0`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.3.0
.. _`v0.2.2`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.2.2
.. _`v0.2.1`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.2.1
.. _`v0.2.0`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.2.0
.. _`v0.1.4`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.1.4
.. _`v0.1.3`: https://github.com/rnd-team-dev/plotoptix/releases/tag/v0.1.3

