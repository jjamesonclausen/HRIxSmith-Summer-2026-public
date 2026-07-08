---
Created: 2026-07-06
Source: [[vj24]]
Tags: #designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
Swept area (m^2): 36
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## 3-Bladed Straight-Bladed Darrieus VAWT

This page covers the single straight-bladed Darrieus example used in `vj24` to test inverse airfoil redesign. (source: sources/vj24.md)

- The rotor has `3` straight blades. (source: sources/vj24.md)
- The baseline blade section is `NACA 0018`, later modified into `NACA 0018-M` through the inverse-design workflow. (source: sources/vj24.md)
- The blade chord is `0.125 m`, blade length is `6 m`, and rotor diameter is `6 m`, giving a swept area of `36 m^2`. (source: sources/vj24.md)
- The rotor mid-span height is `3.048 m` above ground. (source: sources/vj24.md)
- The evaluated operating case fixes wind speed at `12 m/s`, rotational speed at `30 rad/s`, and wind-shear exponent `alpha_w = 0.16`. (source: sources/vj24.md)
- The study neglects struts, tower wake, and finite-span effects in the example case. (source: sources/vj24.md)
- Dynamic stall is modeled with Berg's version of the Gormont model using `AM = 1000`. (source: sources/vj24.md)
- For the baseline `NACA 0018` XFOIL-plus-experiments case, the paper reports `1.610 kW`, `CP = 0.294`, and `CQ = 0.184`. (source: sources/vj24.md)
- For the modified `NACA 0018-M` case, it reports `1.850 kW`, `CP = 0.338`, and `CQ = 0.211`. (source: sources/vj24.md)

> Uncertainty: the paper does not present whole-turbine startup, rated, cut-in, or cut-out values, and it explicitly warns that the reported gain should be treated as a relative prediction because low-Re post-stall analysis remains imperfect. (source: sources/vj24.md)

Related: [[Straight-bladed Darrieus]], [[Darrieus Turbine]], [[PROFOIL]], [[vj24 Blade Airfoil]]

#designs
