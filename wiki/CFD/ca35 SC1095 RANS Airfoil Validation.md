---
Created: 2026-07-17
Updated: 2026-07-17
Sources:
  - "[[ca35]]"
Source_count: 1
tags:
  - CFD
---
# ca35 SC1095 RANS Airfoil Validation

## Scope

This paper compares independently developed two-dimensional RANS predictions for the SC1095 helicopter-rotor airfoil with ten correlated wind-tunnel datasets, across the tested angle-of-attack and Mach-number ranges from `M = 0.3` to `1.0`. The findings are airfoil and rotorcraft-specific evidence, not a VAWT validation case. (source: sources/ca35.md)

## Cases and setup evidence

- The five participating solver/model combinations were OVERFLOW, FUN2D, CFL3D, Cobalt UCB, and TURNS; four used Spalart-Allmaras and CFL3D used Baldwin-Lomax in the main comparison. (source: sources/ca35.md)
- All but one mesh used a structured C-grid; reported structured grids ranged from `217 x 91` to `600 x 150`, and the AED unstructured mesh contained `29,000` nodes. First normal spacing ranged from `1 x 10^-6` to `5 x 10^-5` chord. (source: sources/ca35.md)
- The RANS cases were fully turbulent. The separate MSES comparison solves steady Euler flow on a streamline grid with a finite-volume discretization and an integral two-equation boundary-layer treatment; it allowed free transition up to `10%` chord. (source: sources/ca35.md)
- Investigators did not use one common Reynolds-number scaling: most used a Mach-scaled value per foot or per chord, whereas one used a constant `Re = 6.5 x 10^6`. (source: sources/ca35.md)

## Verification findings

- A coarse-grid calculation predicted early negative stall that disappeared after grid refinement; a separate Cobalt calculation on a similarly coarse grid also produced the early separation. The authors therefore state that grid-refinement studies are needed before confidence in a particular CFD analysis. (source: sources/ca35.md)
- On the refined Cobalt grid, Spalart-Allmaras, Menter SST, and `k-omega` differed little in linear aerodynamics, but differences appeared in stall and transonic conditions. Baldwin-Lomax performed poorly in the comparisons and is not recommended by the paper. (source: sources/ca35.md)
- The authors state that surface-point count and first off-wall spacing must satisfy the selected code and turbulence model's recommended `y+` range; otherwise a grid-refinement study is warranted. (source: sources/ca35.md)
- Fully turbulent CFD typically under-predicted maximum lift-to-drag ratio because it predicted higher drag than the mostly untripped tests. The source states that moderate-Reynolds-number airfoils with laminar flow need boundary-layer-transition modelling for accurate drag and `L/D`. (source: sources/ca35.md)

![Figure 3. Comparison of lift curve slope multiplied by Prandtl-Glauert compressibility correction to Log(Re).](../../images/ca35-fig3.jpg)
Figure 3. Comparison of lift curve slope multiplied by Prandtl-Glauert compressibility correction to Log(Re). [[ca35|Source]]

## Applicability limit

MSES performed well for the source's linear-angle-of-attack cases at subcritical `M <= 0.6`, but departed from the experimental and RANS results in the transonic regime. The authors present this as a lower-cost option only in the stated regime. (source: sources/ca35.md)

> Uncertainty: this is a 2004, two-dimensional SC1095 rotorcraft-airfoil comparison. It supports mesh-refinement, wall-resolution, transition-modelling, and matched-data validation checks, but it does not establish a turbulence model, mesh density, or `y+` target for a low-Reynolds-number rotating VAWT. (source: sources/ca35.md)

Related pages: [[CFD]], [[CFD and Validation]], [[SimScale VAWT Mesh and Quality]], [[ca33 ANSYS Airfoil Validation Workflow]].
