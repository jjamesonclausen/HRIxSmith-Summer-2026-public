---
Created: 2026-07-06
Updated: 2026-07-07
Sources:
  - "[[va27]]"
Source_count: 1
tags:
  - summaries
---
## va27 Summary

High-fidelity CFD airfoil-shape characterization for a low-solidity Darrieus H-type VAWT in deep dynamic stall, focused on the coupled effects of thickness, thickness position, and leading-edge radius. (source: sources/va27.md)

![Source figure](va27-fig14.jpg)
Original caption: Fig. 14. Turbine CP in t/c - xt/c space. Each contour plot is based on 42 simulations. Note the difference in range of colormaps. [[va27|Source]]
![Source figure](va27-fig15.jpg)
Original caption: Fig. 15. Optimal airfoil shapes for lambda = 2.5 and 3.0. [[va27|Source]]

Key points:
- The paper evaluates `126` symmetric NACA-type airfoil shapes built from `6` thickness values, `7` chordwise thickness-position values, and `3` leading-edge radius index values, with `252` transient CFD runs across `lambda = 2.5` and `3.0`. (source: sources/va27.md)
- The study finds that the three shape-defining parameters are strongly coupled, so optimizing one while holding the others fixed can miss the global optimum. (source: sources/va27.md)
- At `lambda = 2.5`, the reported optimal airfoil is `NACA0024e4.5/3.5`, while at `lambda = 3.0`, the optimum shifts to `NACA0018e4.5/2.75`. (source: sources/va27.md)
- In general, reducing the leading-edge radius index from the default `6.0` to `4.5` increases turbine `CP`, especially near the optimal thickness-position combinations. (source: sources/va27.md)
- The paper frames these results as a step toward smart or morphing VAWT blades that adapt airfoil shape to changing tip-speed ratio. (source: sources/va27.md)

Related concepts: [[Morphing Airfoil]], [[Optimization]], [[CFD]], [[Dynamic Stall]], [[va27 Airfoil Relative Maximum Thickness]], [[va27 Airfoil Maximum-Thickness Position]], [[va27 Leading-Edge Radius Index]]

#summaries
