---
Created: 2026-07-02
Source: "[[vj8]]"
tags:
  - designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 0.1837
max Cp (8-12 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
max TSR (8-12 m/s): 
Swept area (m^2): 
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## Contra-rotating VAWT

A VAWT concept that uses two coaxial rotors spinning in opposite directions. This page covers the specific `vj8` CRVAWT optimization study rather than the broader contra-rotating review literature. (source: sources/vj8.md)

## Geometry

- The modeled turbine uses an upper rotor and a lower rotor, each with two NACA0021 blades connected by brackets. (source: sources/vj8.md)
- The two rotors are coaxial and rotate in opposite directions, with a disk generator between them and a floating platform at the bottom. (source: sources/vj8.md)
- Rotor radius is 1000 mm, rotor height is 1200 mm, blade chord is 265 mm, and baseline rotor spacing is 300 mm. (source: sources/vj8.md)
- The baseline blade pitch angle is 6 degrees. (source: sources/vj8.md)

![Source figure](vj8-fig3.jpg)
Original caption: Fig. 3. Model and parameters of CRVAWT. [[vj8|Source]]

## Unique Design Choices

- The study optimizes four specific design variables: blade pitch angle, relative airfoil thickness, rotor spacing, and included angle between the two rotors. (source: sources/vj8.md)
- The source frames the design around offshore use, where low total torque is valuable for platform stability. (source: sources/vj8.md)

## Performance

- Before optimization, the CRVAWT has lower power coefficient than the isolated VAWT but better stability. (source: sources/vj8.md)
- After optimization, Cp reaches 0.1837, which the paper reports as a 36.68% increase over the pre-optimization CRVAWT. (source: sources/vj8.md)
- The optimized CRVAWT reaches 99.19% of the isolated-VAWT single-rotor power coefficient while reducing total torque to 3.04% of the isolated VAWT. (source: sources/vj8.md)
- The optimized values reported by the paper are 1.2 degrees pitch angle, 19.7% relative airfoil thickness, 449.4 mm rotor spacing, and 0 degrees included angle. (source: sources/vj8.md)
- The source says excessively small spacing causes strong rotor interference, while excessively large spacing raises the center of gravity and hurts stability. (source: sources/vj8.md)

![Source figure](vj8-fig17.jpg)
Original caption: Fig. 17. Response surface fitting results. [[vj8|Source]]

## Related

- [[vj8 Contra-rotating VAWT|Contra-rotating VAWT]]
- [[Optimization]]
- [[vj12 Counter-rotating Dual-Rotor VAWT]]

#designs
