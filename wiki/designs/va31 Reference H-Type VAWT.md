---
Created: 2026-07-20
Source: "[[va31]]"
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
# va31 Reference H-Type VAWT

## Geometry

- The reference turbine is a two-bladed straight H-type VAWT using NACA0018 airfoil sections. (source: sources/va31.md)
- Diameter and height are each `1 m`; chord is `0.06 m`; solidity is `0.12`; blade aspect ratio `H/c` is `16.67`; shaft diameter is `0.04 m`. The resulting swept area is `1 m^2`. (source: sources/va31.md)
- The CFD model includes the shaft but omits spokes and blade connections. (source: sources/va31.md)

## Reference operation and model

- The reference condition uses `U_infinity = 9.3 m/s`, `TSR = 4.5`, `Omega = 83.8 rad/s`, `Re_c = 1.76 x 10^5`, and `5%` approach-flow turbulence intensity. (source: sources/va31.md)
- It is represented with 2D URANS transition SST and a sliding-grid interface. The authors justify 2D as a mid-plane model for this high-aspect-ratio rotor, not as a model of its tip losses or support structure. (source: sources/va31.md)

## Reported performance behavior

- At the fixed-`Re_c` tip-speed-ratio sweep, the reported optimum is `TSR = 4.0`; thrust coefficient increases with tip-speed ratio. (source: sources/va31.md)
- The source evaluates `Cp`, `Ct`, blade loads, and wake behavior over operational ranges, but does not report a rated power, cut-in speed, or a complete physical-turbine performance curve. (source: sources/va31.md)

> Uncertainty: this is a CFD reference geometry rather than a complete manufacturable turbine specification. Spoke geometry, blade connection details, surface roughness, and tip losses are absent from the model. (source: sources/va31.md)
