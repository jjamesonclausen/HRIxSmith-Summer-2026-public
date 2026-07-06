---
Created:
Updated: 2026-07-03
Sources:
- [[va10]]
- [[va15]]
- [[va14]]
- [[va11]]
- [[va23]]
- [[va7]]
- [[vj11]]
- [[vj5]]
- [[vj6]]
- [[vj15]]
Source_count: 10
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
- The va14 study says reduced frequency is an influential parameter in VAWT aerodynamic performance and shows that higher solidity or fewer blades can change the scale and timing of dynamic-stall-driven load fluctuations. (source: sources/va14.md)
- It also links higher reduced frequency to delayed separation and changed leading-edge flow behavior in its constant-`Rec` comparisons. (source: sources/va14.md)
- The va15 experiment adds that a small negative pitch angle can delay stall in the upwind region and increase low-`lambda` torque, while rougher blades can also delay stall by promoting earlier transition. (source: sources/va15.md)
- It also shows that these startup gains can disappear or reverse at higher `lambda` or lower solidity. (source: sources/va15.md)
- The vj15 study adds that harmonic variable pitch can suppress flow separation, reduce wake loss, and keep the effective angle of attack below the stall angle in the best case. (source: sources/vj15.md)
- The CFD review treats dynamic stall as one of the central aerodynamic challenges in VAWT development alongside blade-wake interaction and changing angle of attack. (source: sources/vj6.md)
- It also uses dynamic stall as part of the motivation for comparing mesh strategies, turbulence models, and validation approaches. (source: sources/vj6.md)
- The helical-VAWT helix-angle study analyzes leading-edge vortex formation, flow separation, and wake interaction through z-vorticity contours, linking those flow features to secondary peaks in moment coefficient. (source: sources/va7.md)
- The va23 shifted-troposkien paper says the rising low-TSR side of the power curve is dominated by dynamic stall behavior, while the post-peak performance drop is increasingly shaped by secondary effects including blade-wake interaction. (source: sources/va23.md)
- The va24 variable-pitch study treats stall avoidance as the central control objective, explicitly choosing local angle-of-attack targets just below stall so lift stays high and drag stays controlled through the cycle. (source: sources/va24.md)

The VAWT review says dynamic stall is driven by leading-edge vortex growth and shedding, plus blade-vortex interaction on the downwind pass. (source: sources/vj11.md)
It notes that the lift overshoot during dynamic stall can reach about 50% above the static maximum lift coefficient. (source: sources/vj11.md)
It treats low TSR operation as the regime where angle-of-attack excursions most strongly trigger dynamic stall and torque troughs. (source: sources/vj11.md)

Related:
- [[VAWT]]
- [[Darrieus Turbine]]
- [[CFD]]
