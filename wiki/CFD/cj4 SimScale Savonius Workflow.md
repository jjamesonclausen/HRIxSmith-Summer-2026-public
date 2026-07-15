---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj4]]"
Source_count: 1
tags:
  - cfd
---
# cj4 SimScale Savonius Workflow

## Setup outline

- The source describes a quick SimScale setup for a semicircular Savonius VAWT starting from an `IGES` or `STEP` CAD file. (source: sources/cj4.md)
- It says a surrounding air boundary is created first, then boolean subtraction is used so the final flow region contains the turbine shape embedded within the air volume. (source: sources/cj4.md)
- The tutorial selects an incompressible-fluid simulation with air as the working fluid. (source: sources/cj4.md)

## Boundary conditions and outputs

- The stated boundary conditions are an inlet velocity of `11 m/s` in the positive `x` direction and a zero-pressure outlet. (source: sources/cj4.md)
- The remaining boundaries are set as slip walls in this quick setup. (source: sources/cj4.md)
- The post-processing shown includes cutting planes, horizontal-plane velocity views, pressure views, forces and moments, and particle tracing. (source: sources/cj4.md)

## Practical troubleshooting and limits

- The speaker reports deleting conflicting bottom geometry and removing individual solid parts after subtraction to avoid errors in the flow-region model. (source: sources/cj4.md)
- The transcript says default meshing is retained because further adjustment took too long for the quick tutorial. (source: sources/cj4.md)
- It also shows an orientation check: when particle tracing failed to show expected flow around the turbine, the setup was reinterpreted by checking pressure and cross-sectional behavior and then switching the orientation. (source: sources/cj4.md)

> Uncertainty: the transcript does not specify the turbulence model, domain dimensions, rotational treatment, or any validated performance metrics. It is useful as a beginner SimScale workflow example, not as a reproducible Savonius benchmark. (source: sources/cj4.md)

Related pages: [[cj4-summary]], [[CFD]], [[CFD and Validation]], [[SimScale]]

#cfd
