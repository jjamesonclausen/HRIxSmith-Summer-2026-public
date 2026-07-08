---
Created: 2026-07-06
Source: [[va26]]
Tags: #designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 4
Swept area (m^2): 1
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 7
Rated power (W): 
---
## 3-Bladed H-Type VAWT

The `va26` paper studies a low-solidity 3-bladed H-type VAWT and uses it to examine how fixed blade pitch changes aerodynamic loading, wake generation, and average power. (source: sources/va26.md)

## Geometry

- The turbine has `3` NACA0015 blades. (source: sources/va26.md)
- Reported geometry is diameter `1 m`, height `1 m`, swept area `1 m^2`, and solidity `0.172`. (source: sources/va26.md)
- The chord-to-radius ratio is `0.115`, and the operating case studied most closely is `TSR = 4` with freestream velocity `7.0 m/s`. (source: sources/va26.md)

![Source figure](va26-fig3.jpg)
Original caption: Fig. 3. Computational domain for the VAWT (not to scale). [[va26|Source]]
![Source figure](va26-fig10.jpg)
Original caption: Fig. 10. Comparison of calculated power coefficient against experimental and numerical data by Castelli et al. [69]. [[va26|Source]]

## Unique Design Choices

- The source intentionally chooses a low-solidity H-rotor and a moderate TSR to reduce flow complexity and avoid dynamic stall in the zero-pitch baseline case. (source: sources/va26.md)
- The study treats fixed pitch angle as a simple practical modification that can improve performance without major manufacturing or maintenance penalties. (source: sources/va26.md)

## Performance

- The optimum reported fixed pitch angle is `-2` degrees, which increases `Cp` by about `6.6%` relative to zero pitch. (source: sources/va26.md)
- The same optimum also increases `CT` by about `2%` and makes the wake approximately symmetric because `CY` is near zero. (source: sources/va26.md)
- A positive pitch of `+3` degrees produces strong power loss because the blade stalls in the upwind part of the cycle. (source: sources/va26.md)
- The paper also says more negative pitch than `-6` degrees stops helping because flow separation grows in the downwind quartile. (source: sources/va26.md)

## Related

- [[H-VAWT]]
- [[Straight-bladed Darrieus]]
- [[Dynamic Stall]]
- [[va26 Fixed Blade Pitch Angle]]

#designs
