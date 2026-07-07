---
Created: 2026-07-07
Source: [[vj25]]
Tags: #designs
max Cp (1-4 m/s):
max Cp (4-8 m/s):
Efficiency (%):
max TSR (1-4 m/s):
max TSR (4-8 m/s):
Swept area (m^2): 3.509
Cut-in speed (m/s):
Cut-out speed (m/s):
max starting torque (Nm), (0-3 m/s):
Rated speed (m/s): 10
Rated power (W): 1000
---

## 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)

This page covers the lower-aspect-ratio case-study turbine from `vj25`, using the converged `h/R = 0.4` design values. (source: sources/vj25.md)

- The turbine has `2` straight blades with a symmetric `NACA 0018` airfoil. (source: sources/vj25.md)
- The source sets rated power to `1 kW`, design wind speed to `10 m/s`, air density to `1.2 kg/m^3`, and kinematic air viscosity to `1.46 x 10^-5 m^2/s`. (source: sources/vj25.md)
- In the converged case, the rotor aspect ratio is `0.4`, rotor radius is `2.094 m`, blade chord is `0.314 m`, and rotational speed is `137 rpm`. (source: sources/vj25.md)
- Using `h = AR * R`, the blade height is `0.838 m`; with rotor diameter `4.188 m`, the swept area is `3.509 m^2`. (source: sources/vj25.md)
- The converged design values are `cpmax = 0.475`, `sigma_cpmax = 0.3`, `lambda_cpmax = 3.01`, and second-attempt `Re = 6.5 x 10^5`. (source: sources/vj25.md)
- The paper treats this lower-`AR` design as the better-performing option of the two case-study rotors. (source: sources/vj25.md)

> Uncertainty: the paper presents this as a design-method case study, not as an experimentally validated turbine, and it does not report cut-in, cut-out, startup torque, or off-design power-curve values. (source: sources/vj25.md)

Related: [[H-VAWT]], [[Multiple Stream Tube Model]], [[vj25 Rotor Aspect Ratio]], [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]]

#designs
