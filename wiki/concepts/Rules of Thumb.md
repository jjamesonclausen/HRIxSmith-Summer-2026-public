---
Created: 2026-07-01
Updated: 2026-07-08
Sources:
  - "[[vj6]]"
  - "[[vj1]]"
  - "[[vj7]]"
  - "[[vj8]]"
  - "[[vj21]]"
  - "[[vj28]]"
Source_count: 6
tags:
  - concepts
---
## Rules of Thumb

These are practical heuristics supported by the sources. They are not laws.

- If the site has changing wind direction or tight space, start with a VAWT because yaw is not needed and maintenance can stay at ground level. (source: sources/vj1.md, sources/HRI2526.md)
- If self-starting matters more than top efficiency, look hard at Savonius or hybrid concepts. (source: sources/vj2.md, sources/n2.md)
- If you want smoother torque, consider helical blades or other load-smoothing layouts. (source: sources/vj4.md, sources/va7.md)
- If low TSR operation is expected, treat dynamic stall as a first-order design problem. (source: sources/vj5.md, sources/vj6.md)
- If a design is still in CFD, check both 2-D and 3-D modeling assumptions before trusting the results. (source: sources/vj6.md)
- If maintenance access matters, favor ground-level drivetrain placement. (source: sources/vj1.md)
- If blade life matters, prioritize fatigue strength, stiffness, low density, and corrosion resistance. (source: sources/vj7.md)
- If you are tuning a detailed design, start with pitch angle, airfoil thickness, rotor spacing, and included angle. (source: sources/vj8.md)
- If you need a quick performance snapshot, look first at TSR, Cp, torque, starting torque, swept area, and Reynolds number. (source: sources/HRI2526.md, sources/vj1.md)
- If you are building a small fixed-pitch straight-bladed VAWT, avoid very low aspect ratio and treat blade airfoil, strut drag, solidity, and blade material as first-order decisions. (source: sources/vj21.md)
- If you are choosing a blade section for a small fixed-pitch straight-bladed Darrieus rotor, start from a low-Re asymmetric thick airfoil with camber, a generous leading-edge radius, and a sharp trailing edge instead of defaulting to an older symmetric `NACA` section. (source: sources/vj28.md)
- If low-speed starting torque matters, expect higher solidity and three blades to help, but accept some sacrifice in high-speed efficiency or cost. (source: sources/vj21.md)
- If you need a first-pass cut-out target for a smaller-capacity SB-VAWT, the paper treats about `25 m/s` as a typical value. (source: sources/vj21.md)

Related:
- [[Design Checklist]]
- [[Optimization]]
- [[CFD and Validation]]
