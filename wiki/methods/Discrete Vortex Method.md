---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[vj17]]
Source_count: 1
Tags: #methods
---
## Discrete Vortex Method

Discrete vortex method models unsteady flow by discretizing the geometry into panels and placing vortices on the panels. The `vj17` paper uses DVM as the fast first-stage solver for Savonius airfoil optimization. (source: sources/vj17.md)

![Source figure](vj17-fig2.jpg)
Original caption: Fig. 2. Discretization of the airfoils. [[vj17|Source]]

- The method assumes inviscid, irrotational, incompressible, unsteady flow with no body forces. (source: sources/vj17.md)
- It uses control points, Kutta conditions, and Kelvin's theorem to close the system. (source: sources/vj17.md)
- The paper validates the DVM code against Savonius experiments from Sheldahl et al. (source: sources/vj17.md)

Related: [[Savonius Turbine]], [[Optimization]], [[CFD and Validation]]

#methods
