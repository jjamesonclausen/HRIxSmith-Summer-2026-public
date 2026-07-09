---
Created: 2026-07-06
Updated: 2026-07-07
Sources:
  - "[[va22]]"
Source_count: 1
tags:
  - summaries
---
## va22 Summary

Design-and-validation paper for a `100 W` urban-targeted helical VAWT, combining IEC-based sizing, a low-TSR mathematical model with CFD-derived airfoil coefficients, and wind-tunnel testing. (source: sources/va22.md)

![Source figure](va22-fig6.jpg)
Original caption: Figure 6. 100-W helical-blade vertical-axis wind turbine. [[va22|Source]]
![Source figure](va22-fig9.jpg)
Original caption: Figure 9. Graph of power output according to wind velocity obtained from wind tunnel test (symbols: test results; lines: fitting curve). [[va22|Source]]

Key points:
- The paper targets an unusually low design tip-speed ratio of `1.1` for urban use, with rated condition `9 m/s` and `170 rpm`, to reduce noise while keeping helical-blade advantages such as smoother output and better self-starting than conventional straight Darrieus or gyro-mill cases. (source: sources/va22.md)
- The rotor is sized through an IEC `61400-2`-based momentum design and specified as `R = 0.55 m`, `H = 1.43 m`, `A = 1.57 m^2`, `4` blades, solidity `0.3`, and NACA0018 airfoils. (source: sources/va22.md)
- The power-prediction workflow combines a DMS/DMST-style mathematical model with `2D` CFD-derived lift and drag data across the stall region, producing a modeled average output of `108.34 W` and `Cp = 0.154`. (source: sources/va22.md)
- Wind-tunnel testing reports starting wind speed of `3.5 m/s`, measured output of `114.7 W` at the design condition, and a higher peak measured output of `160.2 W` at `9 m/s` when the rotor is allowed to run to `215 rpm`. (source: sources/va22.md)
- The highest reported measured `Cp` in the table is `0.262` at `10 m/s`, while the rated-condition value at `9 m/s` and `170 rpm` is `0.163`. (source: sources/va22.md)

Related concepts: [[Helical VAWT]], [[Wind Turbine Parameters]], [[CFD]], [[Double-Multiple Streamtube Model]], [[Wind Tunnel Testing]]

#summaries
