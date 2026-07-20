---
Created: 2026-07-20
Source: "[[va32]]"
tags:
  - designs
max Cp (1-4 m/s):
max Cp (4-8 m/s):
max Cp (8-12 m/s):
Efficiency (%):
max TSR (1-4 m/s):
max TSR (4-8 m/s):
max TSR (8-12 m/s):
Swept area (m^2): 1
Cut-in speed (m/s):
Cut-out speed (m/s):
max starting torque (Nm), (0-3 m/s):
Rated speed (m/s):
Rated power (W):
---
# va32 Reference H-Type VAWT

## Geometry

- This computational reference turbine has two NACA0018 blades, `D = 1 m`, `c = 0.06 m`, solidity `0.12`, blade aspect ratio `16.67`, and a `0.04 m` shaft. The swept area is `1 m^2`. (source: sources/va32.md)
- The study changes solidity from `0.06` to `0.24` by changing blade chord while keeping blade count fixed. (source: sources/va32.md)

## Reference condition

- The reference condition is `U_infinity = 9.3 m/s`, `TSR = 4.5`, `Omega = 83.8 rad/s`, `Re_c = 176,000`, and `5%` freestream turbulence intensity. (source: sources/va32.md)
- The paper uses this rotor to assess numerical sensitivity, not to establish a full performance curve or a physical design recommendation. (source: sources/va32.md)

> Uncertainty: the source does not specify a physical blade support, tip construction, or measured turbine power for this exact geometry. (source: sources/va32.md)
