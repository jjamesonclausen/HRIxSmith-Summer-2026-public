---
Created: 2026-07-06
Updated: 2026-07-07
Sources:
  - "[[va27]]"
Source_count: 1
tags:
  - concepts
---
## Morphing Airfoil

Airfoil concept in which the blade shape is actively or adaptively changed so the rotor can use a different airfoil geometry at different operating conditions. (source: sources/va27.md)

- The `va27` paper motivates morphing airfoils as a response to the fact that a VAWT with fixed rotor speed experiences different tip-speed ratios as wind speed changes. (source: sources/va27.md)
- Its claim is that the optimal airfoil shape in deep dynamic stall is not the same as the optimal shape at a less severe operating point, so one fixed shape is a compromise. (source: sources/va27.md)
- The paper presents its symmetric-airfoil optimization study as a step toward morphing blades by identifying which shape is best at `lambda = 2.5` and which is best at `lambda = 3.0`. (source: sources/va27.md)
- It reports the optimum shape changing from `NACA0024e4.5/3.5` at `lambda = 2.5` to `NACA0018e4.5/2.75` at `lambda = 3.0`, which is exactly the kind of operating-point dependence that motivates morphing geometry. (source: sources/va27.md)

![Source figure](va27-fig15.jpg)
Original caption: Fig. 15. Optimal airfoil shapes for lambda = 2.5 and 3.0. [[va27|Source]]

Related:
- [[Optimization]]
- [[Dynamic Stall]]
- [[va27 Airfoil Relative Maximum Thickness]]
- [[va27 Airfoil Maximum-Thickness Position]]
- [[va27 Leading-Edge Radius Index]]

#concepts
