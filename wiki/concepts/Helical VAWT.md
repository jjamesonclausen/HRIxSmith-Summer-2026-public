---
Created:
Updated: 2026-07-02
Sources:
- [[sources/HRI2526.md]]
- [[sources/va4.md]]
- [[sources/va7.md]]
- [[sources/vj11.md]]
Source_count: 4
Tags:
- concepts
---
## Helical VAWT

Vertical-axis wind turbine with blades twisted helically around the rotor. (source: sources/va4.md)

- Geometry:
  - The blades are wrapped around the shaft with a helix angle. (source: sources/va4.md, sources/va7.md)
  - The wiki includes both helical Darrieus and helical Savonius variants. (source: sources/HRI2526.md)
- Performance:
  - Helicity spreads loading through the rotation and reduces moment ripple. (source: sources/va4.md, sources/va7.md)
  - In the helix-angle study, 60 degrees gave the best power performance, while larger helix angles reduced Cp variation. (source: sources/va7.md)
- Tradeoffs:
  - Smoother loading comes with added geometric complexity. (source: sources/va7.md)
  - Higher helix angles can reduce peak power even while improving smoothness. (source: sources/va7.md)

The review gives helical Darrieus twist angles of roughly 60-120 degrees and treats helicity as a way to smooth torque ripple across the rotation. (source: sources/vj11.md)
It says helical Darrieus can keep Cp near the straight-blade range while reducing ripple and noise, but at higher manufacturing cost. (source: sources/vj11.md)
It notes that 120 degrees gives smoother loading, while 60 degrees gave the best reported power in the cited comparison. (source: sources/vj11.md)

- The helical layout spreads blade loading across azimuth, which smooths total power output. (source: sources/va4.md)
- In the studied case, the best power coefficient occurs near TSR 1.8. (source: sources/va4.md)
- The paper attributes residual losses to blade-wake interaction, tip vortex, and second flow. (source: sources/va4.md)
- The paper uses LES for the 2D blade-flow study and U-RANS for the full 3D rotor. (source: sources/va4.md)
- Compared with a straight-bladed rotor, the helical rotor is presented as lower-noise and less fluctuation-prone. (source: sources/va4.md)
- A 3D CFD study compared straight, 60-degree, 90-degree, and 120-degree helical VAWTs and found the 60-degree helical blade had the best reported power performance, peaking at TSR 3.3. (source: sources/va7.md)
- In the same study, increasing helix angle reduced the standard deviation of Cp, so the 120-degree helical blade produced smoother cyclic loading than the straight blade while giving lower power performance. (source: sources/va7.md)
- The study found helix angle changes the azimuthal distribution of power production and wake interaction across the rotor cycle. (source: sources/va7.md)

## Figures

![Figure 1: sketch of the HVAWT](../../images/va4-fig1.jpg)
![Figure 14: 2D LES versus 3D U-RANS power coefficient](../../images/va4-fig14.jpg)
![Figure 1: helical blade geometry and helix-angle definition](../../images/va7-fig1.jpg)
![Figure 7: coefficient of performance across helix angles](../../images/va7-fig7.jpg)
![Figure 14: standard deviation of Cp across blade types and TSR](../../images/va7-fig14.jpg)

Related:
- [[VAWT]]
- [[Darrieus Turbine]]
- [[Helical Darrieus]]
- [[CFD]]
- [[Dynamic Stall]]
- [[Aerodynamic Design Parameters]]
