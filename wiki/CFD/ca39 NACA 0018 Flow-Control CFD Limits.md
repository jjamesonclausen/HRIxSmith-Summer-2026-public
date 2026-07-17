---
Created: 2026-07-17
Updated: 2026-07-17
Sources:
  - "[[ca39]]"
Source_count: 1
tags:
  - CFD
---
# ca39 NACA 0018 Flow-Control CFD Limits

## Matched case

The source compares CFL3D and FUN3D RANS calculations with a wind-tunnel NACA 0018 of chord `0.347 m` and span `0.610 m`, at `Re_c = 250,000`, `M = 0.03265`, with a leading-edge blowing slot at `5%` chord and a second `50%`-chord slot not evaluated. The tunnel was `0.610 m` wide by `1.004 m` high. (source: sources/ca39.md)

The two flow-control cases use `C_mu = 5%` and `0.6%`; the reported target slot-exit velocities are `32.693 m/s` and `11.325 m/s`, respectively. (source: sources/ca39.md)

## CFD Evidence

- The authors' fine free-air structured grid used first-cell spacing `2.88 x 10^-6 c` and `Delta y+ < 1`; their grid study found little lift sensitivity across `684,032`, `171,008`, and `42,752` cells, then selected the medium grid for further free-air results. (source: sources/ca39.md)
- For the experiment being compared, upper and lower tunnel walls were only `1.44 c` from the airfoil. Adding inviscid tunnel walls improved calculated pressure distributions and lift relative to free-air calculations; those walls are therefore necessary when directly comparing this setup with its measurements. (source: sources/ca39.md)
- SA and SST, run fully turbulent, gave useful qualitative trends in this specific case. Neither reproduced the experimental nonlinear lift increase between about `5` and `10 degrees`; the tested `gamma-Re_theta` model predicted overly large separated laminar regions and did not reproduce the forward-slot tripping effect. (source: sources/ca39.md)
- In separated high-angle cases, steady RANS commonly oscillated or did not converge. Time-accurate calculations reduced oscillation, but stalled pressure predictions remained poor and did not substantially improve the RANS velocity-field result. (source: sources/ca39.md)
- Preliminary three-dimensional runs found corner and side-wall effects, including an influence on center-plane pressure. The authors therefore limit 2-D CFD here to qualitative analysis, particularly at high angle of attack. (source: sources/ca39.md)

![Figure 12. Comparison between lift coefficient results from a 2-D structured free-air grid and a 2-D structured tunnel grid, no blowing, FUN3D with SA model.](../../images/ca39-fig12.jpg)
Original caption: Figure 12. Comparison between lift coefficient results from a 2-D structured free-air grid and a 2-D structured tunnel grid, no blowing, FUN3D with SA model. [[ca39|Source]]

## Scope Limit

This is not direct validation for a `Re = 50,000` NACA 0018 case: the Reynolds number, tunnel confinement, active leading-edge blowing, transition behavior, and side-wall effects differ. It does not support generalized turbulence-model selection claims. (source: sources/ca39.md)

Related pages: [[CFD]], [[CFD and Validation]], [[cj9 NACA0018 Low-Re Validation Data]], [[Wind Tunnel Testing]].

#CFD
