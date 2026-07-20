---
Created: 2026-07-20
Updated: 2026-07-20
Sources:
  - "[[va32]]"
  - "[[va33]]"
Source_count: 2
tags:
  - cfd
---
# va32 VAWT URANS Computational Guidelines

## Validity scope

These guidelines were developed from `110` validated 2D URANS transition-SST simulations of a two-bladed NACA0018 H-rotor over `1.5 <= TSR <= 5.5` and `0.06 <= solidity <= 0.24`. They control each investigated numerical contribution to predicted `Cp` to below `1%`; they do not establish total CFD error. (source: sources/va32.md)

## Starting settings

- Use a `20D`-wide 2D domain, a `1.5D` rotating core, and a sliding-grid interface for the studied class of H-rotor case. (source: sources/va32.md)
- Place the inlet at least `15D` upstream of the rotor center and the outlet at least `10D` downstream. The former contains the upstream induction field; the latter gives the near wake sufficient development for the target rotor-performance calculation. (source: sources/va32.md)
- Use at least `20-30` revolutions before sampling a statistically steady URANS solution. (source: sources/va32.md)
- Use `0.1 degrees` azimuthal increment for low-to-moderate tip-speed-ratio cases or whenever the separation regime is uncertain. `0.5 degrees` was sufficient only for the study's moderate-to-high tip-speed-ratio attached-flow cases. (source: sources/va32.md)

## Mesh and numerics in the reference case

- The source uses about `400,000` quadrilateral cells, transition SST, second-order temporal and spatial schemes, SIMPLE coupling, and 20 iterations per step to reach scaled residuals below `1 x 10^-5`. Its average/max blade `y+` is `1.37/4`. (source: sources/va32.md)

## Limits

## Earlier moderate-TSR result

- The earlier `va33` study found `10D` upstream sufficient for its single `TSR = 4.5`, solidity-`0.12` case, while the later `va32` sweep selected `15D` to keep the isolated inlet-distance effect below `1%` over more tip-speed-ratio and solidity cases. Use `15D` when following the broader evidence. (source: sources/va33.md, sources/va32.md)

> Uncertainty: do not transfer these settings untested to a 3D turbine, another airfoil, different support geometry, scale-resolving method, or materially different Reynolds number and turbulence level. The authors specifically flag low `Re_c`, blade geometry changes, and non-URANS methods as cases requiring reassessment. (source: sources/va32.md)

Related pages: [[va32 Reference H-Type VAWT]], [[va33 Moderate-TSR Reference H-Type VAWT]], [[va31 Operational Effects on H-VAWT CFD]], [[SimScale VAWT CFD Learning Path]], [[CFD]].
