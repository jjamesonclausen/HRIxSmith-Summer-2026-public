---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj5]]"
Source_count: 1
tags:
  - cfd
---
# cj5 SimScale Virtual Wind Tunnel Workflow

## Setup outline

- The source describes a no-nonsense SimScale workflow for moving from a CAD model to pressure, streamline, and force outputs. (source: sources/cj5.md)
- It begins with importing a `STEP` file, entering CAD mode, creating an external flow volume, and subtracting the solid model from the surrounding air region. (source: sources/cj5.md)
- The original solid is then deleted so the simulation uses only the air-minus-solid flow region. (source: sources/cj5.md)

## Boundary conditions

- The example uses an incompressible simulation with air as the material. (source: sources/cj5.md)
- The tutorial sets a velocity inlet on the front face with a value of `30 m/s` in the positive `Z` direction. (source: sources/cj5.md)
- It sets a zero-gauge-pressure outlet on the opposite face and applies slip-wall conditions on the other four faces. (source: sources/cj5.md)

## Outputs and interpretation

- The source adds a `forces and moments` result control on the model surfaces so lift- or drag-like force components can be plotted over the run. (source: sources/cj5.md)
- It says the early part of the force plot can look erratic and that the most useful value is the stabilized value near the right side of the graph. (source: sources/cj5.md)
- The shown post-processing includes pressure coloring on the model and particle traces started from the inlet wall. (source: sources/cj5.md)

> Uncertainty: the transcript is a generic aircraft-style external-flow tutorial rather than a VAWT case. It does not identify the turbulence model, mesh settings, or any validation comparison, so it is useful as a SimScale workflow template rather than a trustworthy rotor-performance recipe. (source: sources/cj5.md)

Related pages: [[cj5-summary]], [[CFD]], [[SimScale]]

#cfd
