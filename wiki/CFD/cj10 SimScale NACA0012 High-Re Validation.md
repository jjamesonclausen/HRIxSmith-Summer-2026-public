---
Created: 2026-07-16
Updated: 2026-07-16
Sources:
  - "[[cj10]]"
Source_count: 1
tags:
  - cfd
---
# cj10 SimScale NACA0012 High-Re Validation

## Reusable setup details

- The source documents a pseudo-`2D` SimScale airfoil validation workflow using a single-cell extrusion through the spanwise thickness rather than a full 3D span. (source: sources/cj10.md)
- It uses the Standard mesher, not a hex-dominant setup, together with extrusion refinement and a large external domain of `60 m x 40 m`. (source: sources/cj10.md)
- The selected turbulence model is `k-omega SST` with full-resolution near-wall treatment and an inflation strategy targeting `y+ ~ 1`. (source: sources/cj10.md)

## Boundary and coefficient setup

- The inlet velocity is `52.08 m/s`, and the angle of attack is imposed by changing the inlet velocity components to `52.08 * (cos(alpha), sin(alpha))` for each tested angle. (source: sources/cj10.md)
- Lateral faces use `Empty2D`, the outlet pressure is `0`, and the outlet velocity/turbulence fields use zero-gradient conditions. (source: sources/cj10.md)
- The case explicitly uses SimScale's built-in force and moment coefficient result control with defined lift direction, drag direction, reference length, and reference area. (source: sources/cj10.md)

## Mesh and numerics

- The documented mesh-sensitivity test compares coarse (`103,434`), moderate (`218,499`), and fine (`444,101`) meshes at `AoA = 10 deg`, with the moderate mesh selected for the final study. (source: sources/cj10.md)
- The case reports changing the velocity and pressure-gradient interpolation schemes from `Least Squares` to `Gauss-Linear` to improve convergence and stability. (source: sources/cj10.md)

## Limits for current VAWT work

- This is a high-Re, Mach `0.15` airfoil validation pattern, not a low-Re rotating-blade or startup-validation case. (source: sources/cj10.md)
- The large domain, viscosity, and inlet speed are therefore useful as a SimScale reference example, but not as a direct template for low-Re `NACA0012` or `NACA0018` validation at `Re = 50,000`. (source: sources/cj10.md)

> Uncertainty: use this source to learn the structure of a documented SimScale validation case, but do not transfer its numerical values directly into a low-Re VAWT airfoil test without recalculating the Reynolds-number-matched conditions. (source: sources/cj10.md)

Related pages: [[cj10-summary]], [[SimScale]], [[SimScale VAWT Mesh and Quality]], [[CFD and Validation]]

#cfd
