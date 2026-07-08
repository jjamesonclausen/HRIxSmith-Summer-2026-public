---
Created: 2026-07-07
Source: [[vj25]]
Tags: #parameters
Target: increase Cp
Outcome: minimal positive effect
---
## Rotor Aspect Ratio

This `vj25` paper studies rotor aspect ratio in a straight-bladed H-rotor, defining it as `AR = h/R` where `h` is blade height and `R` is rotor radius. (source: sources/vj25.md)

## Parameter

- The source compares two aspect ratios in a `1 kW`, `2`-bladed, `NACA 0018` design case at `10 m/s`: `AR = 2` and `AR = 0.4`. (source: sources/vj25.md)
- It argues that for fixed design power, lowering `AR` increases `R`, which also increases chord `c`, and therefore raises blade Reynolds number. (source: sources/vj25.md)
- The same geometric change also lowers rotational speed because `omega` is inversely proportional to `R` in the paper's design equations. (source: sources/vj25.md)

![Source figure](vj25-fig6.jpg)
Original caption: Fig. 6 How aspect ratio influences Reynolds number and rotational velocity, for different design powers [[vj25|Source]]

## Outcome

- In the converged `AR = 2` case, the paper reports `cpmax = 0.464`, `R = 0.947 m`, `c = 0.189 m`, and `299 rpm`. (source: sources/vj25.md)
- In the converged `AR = 0.4` case, it reports `cpmax = 0.475`, `R = 2.094 m`, `c = 0.314 m`, and `137 rpm`. (source: sources/vj25.md)
- The paper therefore treats lower aspect ratio as aerodynamically favorable because it raises Reynolds number and gives a modest `Cp` increase in the example case. (source: sources/vj25.md)
- It also claims two non-`Cp` benefits for the lower-`AR` rotor: thicker, more stress-resistant blades and greater in-service stability from higher rotor inertia. (source: sources/vj25.md)
- The source's recommendation is strong in direction, but the reported `Cp` gain in the explicit `1 kW` case is small (`0.464` to `0.475`), so this should be treated as a modest improvement rather than a dramatic jump. (source: sources/vj25.md)

## Related

- [[H-VAWT]]
- [[Wind Turbine Parameters]]
- [[Multiple Stream Tube Model]]

#parameters
