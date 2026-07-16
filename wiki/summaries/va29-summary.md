---
Created: 2026-07-16
Updated: 2026-07-16
Sources:
  - "[[va29]]"
Source_count: 1
tags:
  - summaries
---
## va29 Summary

This paper globally optimized circular-arc, Savonius-type VAWTs with two, four, and six blades using a validated transient 3D CFD model and genetic algorithm. (source: sources/va29.md)

- The optimization treated blade geometry and TSR as variables, evaluated approximately `10^5` designs, and reported repeated runs to find the same optimum when populations were sufficiently large. (source: sources/va29.md)
- The model used a half-rotor symmetry domain, sliding mesh, 4-equation transitional SST model, and separate validation against experimental integral cP and local pressure-difference data. (source: sources/va29.md)
- At `AR = 1.5`, the global optima reported cP `0.242` for two blades, `0.318` for four blades, and `0.321` for six blades. (source: sources/va29.md)
- The two-blade optimum operated at TSR `1.2`, used near-zero overlap, and improved cP by 12% relative to the paper's classical `s/d = 0.1` baseline. (source: sources/va29.md)
- The four- and six-blade results were close; the authors infer that more than six blades would be unlikely to add meaningful performance. (source: sources/va29.md)
- Raising aspect ratio toward about `3` increased the six-blade cP from about `0.32` to nearly `0.34`; benefit beyond that was negligible in this study. (source: sources/va29.md)

![Figure 2: Computational zones](../../images/va29-fig2.jpg)
Original caption: Figure 2. Computational zones: a) overall computational domain b) stationary zones near rotor and c) rotor zone. [[va29|Source]]

![Figure 9: Optimized cP-TSR comparison](../../images/va29-fig9.jpg)
Original caption: Figure 9. 3D CFD comparison of cP-TSR of globally optimized blade (2, 4, and 6 blade) with semicircular 2-bladed design with s/d=0.1. [[va29|Source]]

> Uncertainty: the results are CFD-based and validate only against the stated classical-Savonius experiments. The study does not experimentally validate its optimized four- and six-blade geometries. (source: sources/va29.md)

Related pages: [[va29 2-Blade Circular-Arc Savonius VAWT]], [[va29 4-Blade Scooplet Savonius VAWT]], [[va29 6-Blade Scooplet Savonius VAWT]], [[va29 Blade Number]], [[va29 Circular-Arc Blade Profile]], [[va29 Rotor Aspect Ratio]], [[CFD]], [[Savonius Turbine]].

#summaries
