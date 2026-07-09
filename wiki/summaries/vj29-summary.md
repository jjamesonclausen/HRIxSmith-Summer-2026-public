---
Created: 2026-07-09
Updated: 2026-07-09
Sources:
  - "[[vj29]]"
Source_count: 1
tags:
  - summaries
---
## vj29 Summary

This review synthesizes the aerodynamic performance, blade-profile choices, and CFD practices used for H-type Darrieus wind turbines. (source: sources/vj29.md)

- It frames the H-type Darrieus rotor as attractive for omnidirectional, low-wind, and urban applications, but still constrained by poor self-starting torque, low-TSR efficiency loss, and complex unsteady flow driven by dynamic stall and wake interaction. (source: sources/vj29.md)
- It identifies blade profile, pitch angle, solidity, blade number, and TSR as the main recurring design variables in the reviewed H-rotor literature. (source: sources/vj29.md)
- The review says optimized blade profiles can improve `Cp` by about `15%-20%` over conventional `NACA 00xx` sections, with `S1046` highlighted as a strong symmetric candidate, while cambered sections such as `EN0005`, `S815`, `NREL S823`, and `NACA 6712` are presented as stronger low-TSR or self-starting options with possible high-TSR drag penalties. (source: sources/vj29.md)
- It also compiles several passive aerodynamic modifications: slotted or flapped `NACA0018` cases are reported to improve low-TSR `Cp` by about `19%-27%`, blunt trailing edges by about `33%`, and one winglet case by about `10%-19%`. (source: sources/vj29.md)
- For CFD, the review says RANS/URANS formulations dominate about `84%` of the surveyed H-Darrieus simulations, with `k-omega SST` the most common model, while `2D` simulations remain useful for early design but can overpredict `Cp` and miss tip-loss and spanwise-wake physics that require `3D` analysis. (source: sources/vj29.md)
- It closes by highlighting startup, dynamic stall, validation quality, urban-flow uncertainty, and underuse of full `3D` / `FSI` methods as the main research gaps. (source: sources/vj29.md)

![Source figure](vj29-fig5.jpg)
Original caption: Fig. 5. C<sub>p,max</sub> of various airfoils [[vj29|Source]]

![Source figure](vj29-fig8.jpg)
Original caption: Fig. 8. Distribution of turbulence and numerical models that are used in simulations of H-Darrieus rotor [[vj29|Source]]

> Uncertainty: this is a review paper rather than one controlled side-by-side experiment, so several numerical gains come from different studies, Reynolds numbers, and test setups rather than from one common benchmark campaign. (source: sources/vj29.md)

Related pages: [[H-VAWT]], [[Darrieus Turbine]], [[CFD and Validation]], [[Dynamic Stall]], [[vj29 Blade Profile]], [[vj29 Pitch Angle]], [[vj29 Solidity]], [[vj29 Blade Number]]

#summaries
