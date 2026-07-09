---
Created: 2026-07-08
Updated: 2026-07-08
Sources:
  - "[[vj28]]"
Source_count: 1
tags:
  - concepts
---
## Airfoil Selection for Small Straight-Bladed VAWTs

Airfoil-selection framework for smaller-capacity fixed-pitch straight-bladed Darrieus / SB-VAWT rotors, focused on self-starting and low-Reynolds-number performance. (source: sources/vj28.md)

- The paper says this rotor class commonly works in a chord-Reynolds-number band of roughly `100,000` to `500,000`, where laminar separation bubbles, dynamic stall, flow curvature, blade-wake interaction, parasitic strut drag, and turbulence all strongly affect performance. (source: sources/vj28.md)
- It identifies nine desirable aerodynamic characteristics for the airfoil: large low-Re stall angle, wide drag bucket, small zero-lift drag coefficient, large `Cl/Cd`, large maximum lift coefficient, delayed deep stall, small roughness sensitivity, small trailing-edge noise generation, and large negative pitching moment. (source: sources/vj28.md)
- It reduces those targets to four desired geometric features: camber, greater thickness, large leading-edge radius, and sharp trailing edge. (source: sources/vj28.md)
- For fixed-pitch cambered blades, the paper prefers the concave-out configuration, because the upstream pass sees positive incidence and contributes most of the extracted energy. (source: sources/vj28.md)
- It explicitly argues that the older symmetric `NACA` 4-digit sections widely reused in SB-VAWT work are a poor fit for this application, and that a high-lift, low-drag asymmetric thick airfoil is more appropriate. (source: sources/vj28.md)
- The public-domain candidate comparison still shows tradeoffs rather than one universally best section: `S1210` is strongest on several positive-incidence force metrics, `NLF(1)-0416` has the widest low-Re drag bucket, `LS(1)-0417` is least roughness-sensitive in `Cdo`, and `NACA 4415` is the quietest in the model-based noise comparison. (source: sources/vj28.md)

![Source figure](vj28-fig22.jpg)
Original caption: Figure 22. Geometric Features of a Typical Asymmetric Airfoil [[vj28|Source]]

> Uncertainty: the paper's framework is stronger as a screening guide than as proof of one best airfoil, because some results rely on `XFOIL` plus extrapolated post-stall data and several dedicated VAWT airfoils could not be fully evaluated. (source: sources/vj28.md)

Related:
- [[Straight-bladed Darrieus]]
- [[H-VAWT]]
- [[Dynamic Stall]]
- [[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]]
- [[XFOIL]]
- [[NAFNoise]]
- [[vj28 Blade Airfoil]]

#concepts
