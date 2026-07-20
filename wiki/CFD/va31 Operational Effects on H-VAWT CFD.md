---
Created: 2026-07-20
Updated: 2026-07-20
Sources:
  - "[[va31]]"
Source_count: 1
tags:
  - cfd
---
# va31 Operational Effects on H-VAWT CFD

## Scope

These results are for a two-bladed, low-solidity (`0.12`) NACA0018 H-type rotor represented by 2D transition-SST URANS. They are useful hypotheses and setup checks for an H-VAWT, not universal performance predictions. (source: sources/va31.md)

## Tip-speed ratio

- At approximately fixed `Re_c = 2.0 x 10^5`, the source reports maximum `Cp` at `TSR = 4.0`. Below `TSR = 3.0`, blade angle-of-attack variation exceeds the reported `17.5 degrees` static-stall angle and produces dynamic stall. (source: sources/va31.md)
- The upwind quartile supplies more than half of the total power in every examined tip-speed-ratio case; at the optimum `TSR = 4.0`, its contribution is about `68%`. (source: sources/va31.md)
- A fixed-speed rotor is suboptimal away from one wind speed. Holding this rotor at `TSR = 4.0` raised reported `Cp` by up to `168%` at `4 m/s` relative to one listed fixed-speed case. (source: sources/va31.md)

## Reynolds number and turbulence

- Across the studied range, increasing chord Reynolds number advances transition, delays separation, increases `Cl_max`, and reduces `Cd`; the reported `Cp` increase from roughly `0.4 x 10^5` to `4.0 x 10^5` is `77%` at `TSR = 4.0` and `682%` at `TSR = 2.5`. (source: sources/va31.md)
- At `TSR = 2.5`, increasing turbulence intensity from `0%` to `30%` raises the reported `Cp` by `249%` by delaying stall. At `TSR = 4.0`, `5%` turbulence is the reported optimum: `Cp` is `7%` higher than at `0%`, but it falls `9%` by `30%` turbulence. (source: sources/va31.md)

## Interpretation limit

> Uncertainty: the reported effects are from a 2D, low-solidity NACA0018 rotor. The source says that an optimum tip-speed ratio changes with turbine characteristics, while its 2D model omits support drag and tip effects. (source: sources/va31.md)

Related pages: [[va31 Reference H-Type VAWT]], [[va32 VAWT URANS Computational Guidelines]], [[Dynamic Stall]], [[Reynolds Number]].
