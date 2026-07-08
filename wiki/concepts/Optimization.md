---
Created: 2026-07-01
Updated: 2026-07-07
Sources: [[vj8]], [[vj2]], [[va2]], [[vj12]], [[vj11]], [[vj15]], [[vj17]], [[va27]], [[vj18]], [[vj20]], [[vj27]]
Source_count: 11
Tags: #concepts
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
The vj15 study gives a concrete variable-pitch example: harmonic pitch functions with a 3-degree amplitude, especially Case 1, outperform the other tested functions and amplitudes. (source: sources/vj15.md)
The vj17 study adds a three-step optimization workflow for a Savonius airfoil, coupling DVM, CST, and SSA and then verifying the final geometry with CFD. (source: sources/vj17.md)
The va27 study adds a coupled airfoil-shape optimization view for VAWTs in deep dynamic stall, showing that thickness, thickness position, and leading-edge radius must be optimized together rather than one at a time. (source: sources/va27.md)
It also positions this kind of shape map as a precursor to morphing-airfoil design, because the optimum shape changes with tip-speed ratio. (source: sources/va27.md)
It notes that no single enhancement strategy is universally best; the useful objective is usually a multi-objective tradeoff across startup, ripple, loading, and site conditions. (source: sources/vj11.md)
- Optimization is most useful after the concept and basic geometry are fixed. > Inference. (source: sources/vj2.md, sources/vj8.md, sources/va2.md)

- The vj18 review adds a broader optimization taxonomy for variable VAWT design, grouping pitch, flap, Gurney flap, morphing blade, movable mass, synthetic jet, and swept-area strategies by reported gain and complexity. (source: sources/vj18.md)
- It suggests that the useful optimization target is often a tradeoff between performance, self-starting, load smoothing, actuation power, and durability. (source: sources/vj18.md)
- The vj20 hybrid paper adds a DOE-driven geometry optimization stage using Box-Behnken design, response-surface modeling, and CFD databases to tune chord, blade count, shaft distance, pitch angle, and rotor height for `Cp` and cut-in speed. (source: sources/vj20.md)
- The `vj27` review adds a deflector-specific optimization workflow where shape, inclination angle, upstream/downstream position, spacing from the rotor, and deflector length are tuned together rather than one at a time. (source: sources/vj27.md)
- It reports representative gains ranging from about `27%` for simple Savonius flat-plate cases to `50%` for one airfoil-shaped Savonius case and `38.6%` for one kite-shaped twin-turbine case. (source: sources/vj27.md)
Related:
- [[Wind Deflector]]
- [[Variable VAWT Design]]
- [[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]]
- [[CFD and Validation]]
- [[Rules of Thumb]]
- [[vj2 Savonius Shaft Removal]]
- [[vj2 Savonius Placement Outside Darrieus Rotor]]
- [[Morphing Airfoil]]
