---
Created: 2026-07-08
Updated: 2026-07-08
Sources:
  - "[[vj24]]"
  - "[[vj28]]"
Source_count: 2
tags:
  - methods
---
## XFOIL

Interactive subsonic isolated-airfoil analysis code used to generate low-Reynolds-number 2D airfoil aerodynamic data. (source: sources/vj24.md, sources/vj28.md)

- In `vj24`, `XFOIL` is coupled with `PROFOIL` and `CARDAAV` so an inverse-designed low-Re airfoil can be checked and then passed into a straight-bladed Darrieus rotor prediction workflow. (source: sources/vj24.md)
- In `vj28`, `XFOIL` is used to generate lift and drag data for six candidate airfoils over about `-20 deg` to `20 deg` at `RN = 100,000` and `300,000`. (source: sources/vj28.md)
- The same `vj28` workflow also uses `XFOIL` with fixed transition at `10%` chord to compare roughness sensitivity through changes in `alpha_stall`, `Cl,max`, `Cdo`, `Cl/Cd`, and `Cm`. (source: sources/vj28.md)
- The source is explicit that `XFOIL` alone is not enough for the full rotating-blade problem, so high-angle post-stall behavior is extended with `FoilCheck` / Viterna-style extrapolation rather than trusted directly from the core solver. (source: sources/vj28.md)
- `vj28` also notes a practical low-Re limitation: `GOE 420` could not be converged in `XFOIL` at `RN = 100,000`, likely because of low-Re laminar-separation-bubble behavior. (source: sources/vj28.md)

Related: [[PROFOIL]], [[Straight-bladed Darrieus]], [[vj24-summary]], [[vj28-summary]]

#methods
