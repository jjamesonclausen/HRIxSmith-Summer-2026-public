---
Created: 2026-07-17
Updated: 2026-07-17
Sources:
  - "[[ca38]]"
Source_count: 1
tags:
  - concepts
---
# Reynolds Number

The Reynolds number compares inertial and viscous forces for a prescribed flow condition: `Re = rho U_infinity L / mu`, where `U_infinity` is characteristic velocity, `L` is characteristic length, `rho` is density, and `mu` is dynamic viscosity. (source: sources/ca38.md)

- Matching Reynolds number can give similar incompressible flow patterns when velocity and characteristic length differ, provided the other relevant similarity conditions also hold. (source: sources/ca38.md)
- Lower Reynolds-number flow is diffusion-dominated and laminar; higher Reynolds-number flow has stronger inertial effects and can be turbulent, with a transitional regime between. (source: sources/ca38.md)
- Roughness and local acceleration influence transition, so Reynolds number alone does not fully determine the boundary-layer state. (source: sources/ca38.md)

## CFD implication

- The source recommends calculating Reynolds number before CFD modelling to help decide whether transition effects need representation. (source: sources/ca38.md)
- In its circular-cylinder examples, assuming fully laminar flow at about `Re = 1e5` gives an incorrect wake pattern, while assuming fully turbulent flow delays separation and affects lift and drag prediction. (source: sources/ca38.md)
- At its higher-Reynolds-number trans-critical cylinder example, the source says a high-order turbulent scale-resolving simulation is needed to capture the unsteady turbulent vortex structures. (source: sources/ca38.md)

> Uncertainty: the source's numerical regime examples are for pipes, flat plates, and circular cylinders. They are not universal transition thresholds for an airfoil or rotating VAWT blade; use a source-matched airfoil or rotor benchmark to select transition treatment and turbulence modelling.

Related pages: [[CFD]], [[CFD and Validation]], [[Dynamic Stall]], [[ca35 SC1095 RANS Airfoil Validation]].

#concepts
