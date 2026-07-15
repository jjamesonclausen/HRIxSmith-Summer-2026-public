---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj7]]"
Source_count: 1
tags:
  - summaries
---
## cj7 Summary

This source is SimScale documentation for an incompressible rotating-zone simulation using an MRF setup, shown on a quarter-model drone example but directly relevant to rotating-region workflow design. (source: sources/cj7.md)

- The tutorial models only one quarter of the drone by using two symmetry planes, which reduces the computational domain while preserving the rotating-propeller case. (source: sources/cj7.md)
- It uses a flow-region volume with the solid bodies removed plus a cylinder around the propeller to define the rotating region for the MRF setup. (source: sources/cj7.md)
- The atmosphere boundary uses a custom condition with `Pressure inlet-outlet velocity`, total gauge pressure `0 Pa`, and zero-gradient turbulence quantities so the solver can determine local inflow or outflow direction. (source: sources/cj7.md)
- The tutorial sets an MRF rotating zone, changes the number of non-orthogonal correctors to `4` for the tetrahedral mesh, and relies on SimScale's standard physics-based meshing to create the required cell zones automatically. (source: sources/cj7.md)
- Its post-processing workflow emphasizes inspecting the last saved timestep, pressure on the rotating surfaces, seeded particle traces, and cutting-plane vectors through the rotating region. (source: sources/cj7.md)

> Uncertainty: this is a rotating-drone documentation example, not a VAWT benchmark. It supports reusable SimScale rotating-zone workflow details, but not turbine-specific performance claims or VAWT-specific MRF-vs-AMI selection rules. (source: sources/cj7.md)

Related pages: [[CFD]], [[cj7 SimScale MRF Rotating Zone Workflow]], [[SimScale]], [[SimScale VAWT Rotating Region]], [[SimScale VAWT Results and Comparison]]

#summaries
