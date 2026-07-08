---
Created: 2026-07-03
Updated: 2026-07-07
Sources: [[va16]]
Source_count: 1
Tags: #methods
---
## Panel Method

Potential-flow method that models blade and wake vortices without a computational mesh, here coupled with a free-vortex wake and viscosity correction from 2-D airfoil data. (source: sources/va16.md)

![Source figure](../../images/va16-fig1.jpg)
Original caption: Fig. 1. Schematic of (a) the reference turbine, (b) computational domain (both not to scale); (c-e) computational grid near the (c) rotating core, (d) airfoil, and (e) trailing edge. [[va16|Source]]
![Source figure](../../images/va16-fig3.jpg)
Original caption: Fig. 3. Process of viscosity correction in this study. [[va16|Source]]

- The source uses an incompressible potential-flow panel method coupled with a free-vortex wake. (source: sources/va16.md)
- Induced velocity is computed with a Rankine vortex model. (source: sources/va16.md)
- Inviscid sectional lift is corrected using 2-D airfoil characteristic data to account for viscosity. (source: sources/va16.md)
- The paper positions the method as more convenient than CFD for large three-dimensional unsteady parameter sweeps because it does not require computational grids. (source: sources/va16.md)

Related:
- [[Double-Multiple Streamtube Model]]
- [[CFD]]
- [[H-VAWT]]

#methods
