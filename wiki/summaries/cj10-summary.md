---
Created: 2026-07-16
Updated: 2026-07-16
Sources:
  - "[[cj10]]"
Source_count: 1
tags:
  - summaries
---
## cj10 Summary

This source is a SimScale validation-case page for a high-Re `NACA0012` airfoil at Mach `0.15`, useful as a documented SimScale setup pattern for external airfoil CFD rather than as a low-Re VAWT-specific benchmark. (source: sources/cj10.md)

- The case uses turbulent incompressible flow with `k-omega SST`, a pseudo-`2D` setup created by extruding a single cell through the spanwise thickness, and a very large `60 m x 40 m` computational domain. (source: sources/cj10.md)
- It uses the Standard mesher with extrusion refinement, tests three mesh densities, selects a moderate `218,499`-cell mesh, and targets `y+ ~ 1` with full near-wall resolution. (source: sources/cj10.md)
- The angle of attack is imposed through the inlet velocity components rather than by rotating the geometry, using a free-stream speed of `52.08 m/s` and angles `0`, `2.5`, `5`, `10`, and `15` degrees. (source: sources/cj10.md)
- To improve convergence and stability, the case changes the velocity and pressure-gradient interpolation schemes from `Least Squares` to `Gauss-Linear`. (source: sources/cj10.md)

> Uncertainty: this is a high-Re, Mach `0.15` `NACA0012` validation case, so its exact velocity, viscosity, and compressibility context are not directly transferable to very-low-Re airfoil or VAWT startup-validation work. (source: sources/cj10.md)

Related pages: [[CFD]], [[SimScale]], [[cj10 SimScale NACA0012 High-Re Validation]], [[SimScale VAWT Mesh and Quality]], [[CFD and Validation]]

#summaries
