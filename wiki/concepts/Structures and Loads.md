---
Created:
Updated: 2026-07-03
Sources:
- [[HRI2526]]
- [[va8]]
- [[vj1]]
- [[vj4]]
- [[vj5]]
- [[vj8]]
Source_count: 6
Tags:
- concepts
---
## Structures and Loads

This page collects the load and structural issues that shape a VAWT design.

- Dynamic stall is a central load driver at low TSR. (source: sources/vj5.md, sources/vj6.md)
- Torque ripple and cyclic loading matter for rotor smoothness and fatigue. (source: sources/vj1.md, sources/vj4.md, sources/va7.md)
- Stability is a design goal in contra-rotating configurations. (source: sources/vj8.md)
- Blade loads depend on blade number, inclination, and camber line. (source: sources/vj4.md)
- Offshore and urban applications both create structural constraints that show up in VAWT studies. (source: sources/HRI2526.md, sources/vj1.md)
- The va8 patent uses a central vertical rotating shaft, upper and lower hubs, upper and lower channel beams, and two thrust bearings to support side loads, allow shaft rotation, and carry self-weight. (source: sources/va8.md)
- The patent explicitly treats shaft/building-framework connection as a stability measure so the shaft does not bend enough to interfere with free rotation. (source: sources/va8.md)
- It places the generator/storage hardware near the bottom of the turbine and frames that choice as improving stability. (source: sources/va8.md)
- The hybrid-CFD study in `vj2` identifies the internal Savonius shaft as a structural element that also obstructs flow through the blade overlap space, creating a tradeoff between structure and aerodynamic torque. (source: sources/vj2.md)
- The same source says Savonius-generated turbulence can negatively affect the lift-based Darrieus blades when the Savonius rotor sits in the middle of the hybrid rotor. (source: sources/vj2.md)

![Source figure](../../images/va8-fig2.jpg)
Original caption: Figure 2: Vertical cross section of the turbine shaft. [Source](../../sources/va8.md)

Related:
- [[Dynamic Stall]]
- [[Materials and Manufacturing]]
- [[Rules of Thumb]]
- [[Hybrid VAWT]]
- [[vj2 Savonius-Darrieus Hybrid Wind Turbine]]
- [[vj2 Shaftless Savonius-Darrieus Hybrid Wind Turbine]]
