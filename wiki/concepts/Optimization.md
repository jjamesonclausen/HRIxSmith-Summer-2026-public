---
Created:
Updated: 2026-07-03
Sources:
- [[va2]]
- [[vj11]]
- [[vj12]]
- [[vj2]]
- [[vj8]]
Source_count: 5
Tags:
- concepts
---
## Optimization

Use this page when the design has to be tuned rather than just chosen.

- Response surface methods appear in the contra-rotating VAWT study. (source: sources/vj8.md)
- Parameter optimization in the hybrid VAWT paper is driven by CFD results. (source: sources/vj2.md)
- The hybrid paper in `vj2` uses two sequential geometry changes on the same turbine, first removing the internal Savonius shaft and then moving split Savonius halves outside the Darrieus rotor, with reported average torque gains of 10.5% and 22.3%. (source: sources/vj2.md)
- CST parameterization, Kriging surrogate modeling, and a multi-island genetic algorithm are used in VAWT airfoil optimization work. (source: sources/va2.md)
- The vj12 review splits performance improvement into active rotor changes and passive flow-guiding devices. (source: sources/vj12.md)
- It treats counter-rotation, blade shape/profile, twist, inner blades, end plates, and multi-stage stacking as active design levers. (source: sources/vj12.md)
- It treats guide vanes, diffusers, deflectors, siting, and rotor spacing as passive or layout-level optimization levers. (source: sources/vj12.md)
- It reports large single-study gains such as 41% Cp improvement from inner blades, 51% Cp gain from a 180-degree twist case, and a 3x Cp increase from adding a wind deflector in one setup. (source: sources/vj12.md)

The review groups optimization strategies into blade shape, variable pitch, guide vanes, hybridization, helical twist, diffuser/shroud augmentation, solidity tuning, active flow control, and array layout. (source: sources/vj11.md)
It reports typical gains of 5-15% for blade shape optimization, 10-20% for variable pitch, and 10-25% for array layout depending on the case. (source: sources/vj11.md)
It notes that no single enhancement strategy is universally best; the useful objective is usually a multi-objective tradeoff across startup, ripple, loading, and site conditions. (source: sources/vj11.md)
- Optimization is most useful after the concept and basic geometry are fixed. > Inference. (source: sources/vj2.md, sources/vj8.md, sources/va2.md)

Related:
- [[Aerodynamic Design Parameters]]
- [[CFD and Validation]]
- [[Rules of Thumb]]
- [[vj2 Savonius Shaft Removal]]
- [[vj2 Savonius Placement Outside Darrieus Rotor]]
