---
Created: 2026-07-06
Source: [[va22]]
Tags: #designs
max Cp (1-4 m/s): 0.001
max Cp (4-8 m/s): 0.199
Efficiency (%):
max TSR (1-4 m/s):
max TSR (4-8 m/s):
Swept area (m^2): 1.57
Cut-in speed (m/s): 3.5
Cut-out speed (m/s):
max starting torque (Nm), (0-3 m/s):
Rated speed (m/s): 9
Rated power (W): 100
---

## 100-W Helical-Blade Vertical-Axis Wind Turbine

The `va22` paper presents a small helical lift-type VAWT designed for urban use at unusually low tip-speed ratio and then validated in a wind tunnel. (source: sources/va22.md)

## Geometry

- The rotor uses `4` helical blades with NACA0018 airfoils. (source: sources/va22.md)
- Reported design dimensions are rotor radius `0.55 m`, rotor height `1.43 m`, swept area `1.57 m^2`, chord length `0.25 m`, and solidity `0.3`. (source: sources/va22.md)
- The aspect ratio is `1.3`, and the rated rotational speed is `170 rpm`. (source: sources/va22.md)
- The source says the axis, hubs, and struts were designed according to IEC `61400-2`, with FRP blades and a carbon-steel rotating shaft pipe of outer diameter `60.5 mm`. (source: sources/va22.md)

![Source figure](../../images/va22-fig6.jpg)
Original caption: Figure 6. 100-W helical-blade vertical-axis wind turbine. [[va22|Source]]
![Source figure](../../images/va22-fig1.jpg)
Original caption: Figure 1. Basic design parameters of the vertical wind turbine. [[va22|Source]]

## Unique Design Choices

- The source intentionally targets `TSR = 1.1`, much lower than the `4-6` range it cites for conventional Darrieus peak performance, because the urban-use goal prioritizes lower rotational speed and lower noise. (source: sources/va22.md)
- The design method uses CFD-derived lift and drag coefficients across the stall region so the mathematical model can still be applied despite the low-TSR operating point. (source: sources/va22.md)
- Helical blades were selected specifically for lower output fluctuation, lower noise, and better self-starting than conventional Darrieus or gyro-mill blades. (source: sources/va22.md)

## Performance

- The mathematical model predicts `108.34 W` average output and `Cp = 0.154`, which is above the `100 W` target. (source: sources/va22.md)
- Wind-tunnel testing reports a starting wind speed of `3.5 m/s`. (source: sources/va22.md)
- At the design condition of `9 m/s` and `170 rpm`, the measured output is `114.7 W` with `Cp = 0.163`, which the source reports as `5.9%` above the model prediction. (source: sources/va22.md)
- The highest measured output listed in the source table is `304.4 W` at `11 m/s` and `258 rpm`, with the highest listed `Cp` of `0.262` occurring at `10 m/s`. (source: sources/va22.md)
- The source also reports `160.2 W` at `9 m/s` when the rotor is allowed to run at `215 rpm`, above the intended rated speed. (source: sources/va22.md)

## Related

- [[Helical VAWT]]
- [[Wind Turbine Parameters]]
- [[Double-Multiple Streamtube Model]]
- [[Wind Tunnel Testing]]

#designs
