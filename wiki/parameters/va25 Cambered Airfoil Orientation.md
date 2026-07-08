---
Created: 2026-07-06
Source: [[va25]]
Tags: #parameters
Target: improve self-starting and Cp
Outcome: significant positive effect
---
## Cambered Airfoil Orientation

This `va25` study compares cambered-in and cambered-out orientations for several cambered airfoils to see whether simply flipping the camber improves Darrieus VAWT performance. (source: sources/va25.md)

- The source compares both orientations for `NACA6712`, `Clark Y`, `FX63-137`, and `S1210`. (source: sources/va25.md)
- It reports a strong performance increase when the camber is flipped outward for several weak cambered-in cases. (source: sources/va25.md)
- Flipped `Clark Y` becomes the strongest cambered-out case, reaching `Cp = 0.3458` near `TSR = 3.0`, about `6%` above the NACA0021 reference model. (source: sources/va25.md)
- Flipped `NACA6712` also performs well, reaching `Cp = 0.3397` near `TSR = 2.64`, about `4%` above the reference. (source: sources/va25.md)
- The source says flipped `Clark Y` and flipped `S1210` both self-start in the dynamic startup simulation, but flipped `Clark Y` reaches higher TSR sooner and peaks slightly higher (`3.77` versus `3.70`). (source: sources/va25.md)
- The source therefore treats camber orientation as a major performance lever, especially for startup and low-TSR behavior. (source: sources/va25.md)

#parameters
