---
Created: 2026-07-16
Updated: 2026-07-16
Sources:
  - "[[ca33]]"
Source_count: 1
tags:
  - CFD
---
# ca33 ANSYS Airfoil Validation Workflow

## Scope

This tutorial demonstrates a steady, two-dimensional ANSYS Fluent workflow for a `1 m` chord NACA 4415 airfoil at `Re = 6 x 10^6`. It is a workflow example, not a low-Reynolds-number NACA 0018 benchmark. (source: sources/ca33.md)

## Setup elements

- It imports coordinate points as one closed polyline, fills the profile, and subtracts it from a C-type external fluid domain. (source: sources/ca33.md)
- The C-domain extends about `15` chord lengths in its stated lateral and downstream dimensions. (source: sources/ca33.md)
- It uses a two-dimensional, steady, pressure-based calculation with SST `k-omega`, air properties of `rho = 1.225 kg/m^3` and `mu = 1.7894 x 10^-5 kg/(m s)`, a velocity inlet, zero-gauge-pressure outlet, slip outer boundaries, and no-slip airfoil wall. (source: sources/ca33.md)
- It uses a structured quadrilateral mesh with concentrated leading-edge, airfoil, and near-wake cells. (source: sources/ca33.md)

## Angle-of-attack coefficients

When angle of attack is nonzero and the airfoil geometry remains unrotated, the inlet velocity components are `U cos(alpha)` and `U sin(alpha)`. Drag must be projected parallel to the freestream and lift perpendicular to it; the tutorial gives drag direction `(cos(alpha), sin(alpha))` and lift direction `(-sin(alpha), cos(alpha))`. (source: sources/ca33.md)

## Verification sequence

- The tutorial uses a preliminary first-cell-height estimate for target `y+ = 3`, then checks the solved wall-`y+` distribution rather than accepting the estimate alone. (source: sources/ca33.md)
- It monitors lift, drag, and residual histories; its reported result had little residual change after roughly 200 iterations but did not meet its selected `1e-6` criterion by 1,250 iterations. (source: sources/ca33.md)
- It compares the converged coefficients with published data at the same airfoil, Reynolds number, and angle of attack. (source: sources/ca33.md)

> Uncertainty: the tutorial's claimed `10.8%` agreement is for NACA 4415 at `Re = 6 x 10^6` and zero angle of attack. It does not validate SST `k-omega`, its mesh, or its 2D workflow for NACA 0018 at `Re = 50,000`. (source: sources/ca33.md)

Related pages: [[CFD]], [[CFD and Validation]], [[SimScale VAWT Mesh and Quality]], [[SimScale VAWT Domain and Boundaries]].

#CFD
