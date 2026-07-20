---
Created: 2026-07-20
Source: "[[va33]]"
tags:
  - designs
max Cp (1-4 m/s):
max Cp (4-8 m/s):
max Cp (8-12 m/s): 0.41
Efficiency (%):
max TSR (1-4 m/s):
max TSR (4-8 m/s):
max TSR (8-12 m/s): 4.5
Swept area (m^2): 1
Cut-in speed (m/s):
Cut-out speed (m/s):
max starting torque (Nm), (0-3 m/s):
Rated speed (m/s):
Rated power (W):
---
# va33 Moderate-TSR Reference H-Type VAWT

## Geometry

- The reference rotor is a two-bladed NACA0018 H-type VAWT with `D = 1 m`, `H = 1 m`, `c = 0.06 m`, solidity `0.12`, and a `0.04 m` shaft. Its swept area is `1 m^2`. (source: sources/va33.md)
- The 2D and 2.5D CFD geometries omit spokes and tower-connection struts. (source: sources/va33.md)

## Reference condition and outcome

- The turbine operates at `TSR = 4.5`, `U_infinity = 9.3 m/s`, and `Omega = 83.8 rad/s`; its chord-based geometric Reynolds-number range is `100,000-200,000`. (source: sources/va33.md)
- The reported 2D and 2.5D `Cp` are approximately `0.41`, compared with an experimental value of `0.40` for a stated `2.5%` deviation. (source: sources/va33.md)

> Uncertainty: this is a validation-oriented CFD reference, not a complete physical design. The authors identify missing roughness, spokes, struts, and RANS wake limitations as possible sources of its wake discrepancy. (source: sources/va33.md)
