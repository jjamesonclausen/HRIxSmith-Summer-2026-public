---
Created: 2026-07-06
Source: "[[va4]]"
tags:
  - parameters
Target: increase Cp
Outcome: significant positive effect
---
## Tip Speed Ratio

This `va4` study varies turbine tip speed ratio to understand how it changes power output, torque fluctuation, angle of attack, and blade-wake interaction in a four-bladed helical VAWT. (source: sources/va4.md)

## Parameter Change

- The paper compares TSR conditions of 0.9, 1.14, 1.25, 1.46, 1.8, and 2.3. (source: sources/va4.md)
- The baseline turbine geometry is held fixed while TSR is varied to study operating-point sensitivity. (source: sources/va4.md)
- The paper presents TSR as the main combined operating parameter linking rotation speed and wind speed for this turbine. (source: sources/va4.md)
- The experimental turbine is a 2.6:1 scale model of the 3D CFD case, with aspect ratio and blade solidity preserved between the compared cases. (source: sources/va4.md)

![Source figure](va4-fig6.jpg)
Original caption: Figure 6. Power coefficient at different TSR with Reynold number 60,800. [[va4|Source]]

![Source figure](va4-fig7.jpg)
Original caption: Figure 7. The power output at different TSR conditions, (a-f) represent 0.9, 1.14, 1.25, 1.46, 1.8, 2.3 TSR lambda respectively, red line and black lines represent the 2D LES and U-RANS results, respectively. [[va4|Source]]

![Source figure](va4-fig13.jpg)
Original caption: Figure 13. Power fluctuation coefficient at different azimuthal points and TSR conditions, the lines on axis plane are isoline of power fluctuation coefficient. [[va4|Source]]

![Source figure](va4-fig19.jpg)
Original caption: Figure 19. Wake vortex diffusion pattern at 2.3 TSR condition. [[va4|Source]]

## Detailed Results

- The power coefficient varies non-monotonically with TSR and reaches its maximum at TSR 1.8. (source: sources/va4.md)
- The conclusion section reports maximum power output at TSR 1.8 with a power coefficient of 10 percent. (source: sources/va4.md)
- At lower TSR, the turbine experiences larger angle-of-attack excursions; the source says the maximum AOA decreases from about 85 degrees to about 30 degrees as TSR increases across the studied range. (source: sources/va4.md)
- In the upwind half-cycle, power output increases with increasing TSR because the smaller angle of attack reduces severe flow separation. (source: sources/va4.md)
- In the downwind half-cycle, negative power increases as TSR increases, so very high TSR creates stronger self-consumption losses even though upwind performance improves. (source: sources/va4.md)
- The source specifically says net power at TSR 2.3 is lower than at TSR 1.46 or 1.8 because the downwind negative-power penalty becomes too large. (source: sources/va4.md)

## Outcome

- Low TSR causes large angle-of-attack variation and strong torque fluctuation. In the instantaneous-blade-torque plots, TSR 0.9 fluctuates more wildly than TSR 1.46 and 2.3. (source: sources/va4.md)
- As TSR rises from low values toward the optimum, the changing ratio of angle of attack becomes smoother and the power supply becomes more stable through a revolution. (source: sources/va4.md)
- If TSR is increased too far, blade-wake interaction causes a sudden rise in power fluctuation again, so the stability benefit is not monotonic. (source: sources/va4.md)
- The source says an optimized TSR near 1.8 gives not only higher power output but also a more stable power supply for this case at Reynolds number 60,800. (source: sources/va4.md)
- The study therefore presents TSR optimization as a strong lever on performance, with both too-small and too-large TSR causing deterioration, making the effect significant and not merely incremental. (source: sources/va4.md)

## Why It Helps

- Increasing TSR from very low values reduces the extreme angle-of-attack swings that drive separation and unstable torque. (source: sources/va4.md)
- However, excessive TSR also makes the rotating wake more influential, increases negative downwind power, and intensifies blade-wake interaction losses. (source: sources/va4.md)
- The optimum near TSR 1.8 is therefore a balance point between reduced stall/separation at low TSR and increased wake-driven penalties at high TSR. (source: sources/va4.md)

## Related

- [[va4 Four-Bladed Helical VAWT]]
- [[va3 Tip Speed Ratio Classification]]
- [[Helical VAWT]]

#parameters
