---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj7]]"
Source_count: 1
tags:
  - cfd
---
# cj7 SimScale MRF Rotating Zone Workflow

## Model structure

- The source demonstrates an incompressible SimScale workflow using a quarter-model drone with two symmetry planes. (source: sources/cj7.md)
- The geometry contains a fluid flow region with the solid body removed and a cylinder around the propeller that defines the rotating region. (source: sources/cj7.md)
- The documentation presents this flow-region-plus-cylinder convention as the recommended modeling pattern for external rotating geometries in SimScale. (source: sources/cj7.md)

## Boundary and rotating-zone setup

- The drone surfaces use a no-slip wall condition and the two cut planes use symmetry boundary conditions. (source: sources/cj7.md)
- The open outer faces use a custom atmosphere boundary with `Pressure inlet-outlet velocity`, total gauge pressure `0 Pa`, and zero-gradient turbulence quantities. (source: sources/cj7.md)
- The rotating region is created under Advanced concepts as an `MRF rotating zone` and assigned to the rotating-zone volume. (source: sources/cj7.md)

## Mesh and numerics

- The tutorial uses the SimScale standard mesh with default mesh settings. (source: sources/cj7.md)
- It explicitly sets the number of non-orthogonal correctors to `4` to improve the solution for the tetrahedral mesh. (source: sources/cj7.md)
- Because physics-based meshing is used, SimScale creates the needed cell zones automatically for the rotating-zone assignment. (source: sources/cj7.md)

## Post-processing

- The source recommends viewing the last timestep, hiding enclosure walls, and coloring the drone by pressure to inspect high- and low-pressure regions. (source: sources/cj7.md)
- It then uses particle traces seeded below the drone and cutting planes with vectors to inspect accelerated and swirling flow through the rotating region. (source: sources/cj7.md)

> Uncertainty: this is a documented drone example rather than a VAWT validation case. It is strong evidence for SimScale MRF setup mechanics, but not for which rotating-zone model or boundary strategy is best for a particular VAWT objective. (source: sources/cj7.md)

Related pages: [[cj7-summary]], [[SimScale]], [[SimScale VAWT Rotating Region]], [[SimScale VAWT Results and Comparison]]

#cfd
