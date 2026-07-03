---
Created:
Updated: 2026-07-03
Sources:
- [[va10]]
- [[va11]]
- [[va7]]
- [[vj11]]
- [[vj5]]
- [[vj6]]
Source_count: 6
Tags:
- concepts
---
## Dynamic Stall

Unsteady aerodynamic separation that occurs when a blade experiences rapidly changing angle of attack. (source: sources/vj5.md)

- In VAWTs, dynamic stall is intrinsic at low tip speed ratios and affects both loads and power. (source: sources/vj5.md)
- The source treats vorticity shedding and wake roll-up as the key validation targets for modeling dynamic stall. (source: sources/vj5.md)
- URANS models underpredict the phenomenon; DES matches the observed vorticity evolution best. (source: sources/vj5.md)
- PIV data is useful for validating dynamic-stall CFD because it captures vortex structure directly. (source: sources/vj5.md)
- The va10 review treats dynamic stall as one of the major Darrieus CFD application areas and ties it to the need for better transition and unsteady-flow modeling. (source: sources/va10.md)
- It says transition SST predicts flow separation more accurately than classical fully turbulent RANS models in reviewed Darrieus cases. (source: sources/va10.md)
- The va11 wake review treats deep dynamic stall on the windward side as a main cause of H-rotor wake asymmetry and strong vortex shedding. (source: sources/va11.md)
- It also connects dynamic stall to blade-wake interaction in the near wake and to the counter-rotating wake structures that drive recovery. (source: sources/va11.md)
- The CFD review treats dynamic stall as one of the central aerodynamic challenges in VAWT development alongside blade-wake interaction and changing angle of attack. (source: sources/vj6.md)
- It also uses dynamic stall as part of the motivation for comparing mesh strategies, turbulence models, and validation approaches. (source: sources/vj6.md)
- The helical-VAWT helix-angle study analyzes leading-edge vortex formation, flow separation, and wake interaction through z-vorticity contours, linking those flow features to secondary peaks in moment coefficient. (source: sources/va7.md)

The VAWT review says dynamic stall is driven by leading-edge vortex growth and shedding, plus blade-vortex interaction on the downwind pass. (source: sources/vj11.md)
It notes that the lift overshoot during dynamic stall can reach about 50% above the static maximum lift coefficient. (source: sources/vj11.md)
It treats low TSR operation as the regime where angle-of-attack excursions most strongly trigger dynamic stall and torque troughs. (source: sources/vj11.md)

Related:
- [[VAWT]]
- [[Darrieus Turbine]]
- [[CFD]]
