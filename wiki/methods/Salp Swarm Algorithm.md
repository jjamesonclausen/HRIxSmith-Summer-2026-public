---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[vj17]]
Source_count: 1
Tags: #methods
---
## Salp Swarm Algorithm

Salp Swarm Algorithm is a nature-inspired optimization method that splits the population into a leader and followers. The `vj17` paper uses SSA to search CST curvature coefficients for maximum Savonius power coefficient. (source: sources/vj17.md)

![Source figure](vj17-fig4.jpg)
Original caption: Fig. 4. The optimization flowchart. [[vj17|Source]]

- The leader updates position relative to the food source, which represents the global best solution. (source: sources/vj17.md)
- The followers update according to a Newton-law-style rule. (source: sources/vj17.md)
- The paper picks SSA because it is simple, robust, and has few user-defined parameters. (source: sources/vj17.md)

Related: [[Optimization]], [[CST Parameterization]], [[Discrete Vortex Method]]

#methods
