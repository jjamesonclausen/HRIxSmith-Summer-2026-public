---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj5]]"
Source_count: 1
tags:
  - summaries
---
## cj5 Summary

This source is a concise SimScale tutorial for setting up a generic external-flow "virtual wind tunnel" case and extracting pressure and force results from a CAD model. (source: sources/cj5.md)

- The workflow starts from an imported `STEP` model, then creates an external flow volume and subtracts the solid model from the air box before creating an incompressible-air simulation. (source: sources/cj5.md)
- The stated boundary-condition example uses a velocity inlet of `30 m/s` in the positive `Z` direction, a zero-gauge-pressure outlet, and slip walls on the other four faces of the box. (source: sources/cj5.md)
- The tutorial adds a `forces and moments` result control on the solid surfaces and reads the stabilized value on the right side of the force-history plot rather than trusting the early transient-looking part of the graph. (source: sources/cj5.md)
- It also shows post-processing with pressure coloring and particle tracing seeded from the inlet wall. (source: sources/cj5.md)

> Uncertainty: this is a general external-aerodynamics tutorial, not a VAWT study. It does not report a turbulence model, mesh settings, validation case, or any turbine-specific interpretation. (source: sources/cj5.md)

Related pages: [[CFD]], [[cj5 SimScale Virtual Wind Tunnel Workflow]], [[SimScale]]

#summaries
