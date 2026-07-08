---
Created: 2026-07-06
Source: [[va23]]
Tags: #designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 0.24
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
Swept area (m^2): 0.36
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## 100% STS-VAWT

The `100% STS-VAWT` is the more extreme shifted-troposkien `va23` concept, intended so one blade wake affects only that same blade in later revolutions rather than the other blade directly. (source: sources/va23.md)

## Geometry

- The turbine keeps the same `2` blades, radius `0.375 m`, total height `0.75 m`, swept area `0.36 m^2`, and chord length `0.1 m` as the other cases. (source: sources/va23.md)
- Its blade height is `0.375 m`, blade length `0.855 m`, and solidity `0.46`, making it the shortest and lowest-solidity case in the paper. (source: sources/va23.md)
- The blade airfoil remains NACA0015. (source: sources/va23.md)

![Source figure](va23-fig1.jpg)
Original caption: Figure 1. Vertical axis wind turbine (VAWT) configurations: (A) conventional VAWT (troposkien shape), (B) novel 50% STS-VAWT (50% shifted troposkien shape-VAWT), (C) novel 100% STS-VAWT. [[va23|Source]]
![Source figure](va23-fig10.jpg)
Original caption: Figure 10. Power coefficient (Cp) vs TSR before corrections at 700 rpm. [[va23|Source]]

## Unique Design Choices

- The source says the vertical shift is large enough that one blade wake no longer affects the other blade directly. (source: sources/va23.md)
- This further reduces blade-wake interaction, but it also shortens the blades and lowers solidity more than in the `50%` shifted case. (source: sources/va23.md)

## Performance

- At `600 rpm`, the paper reports an uncorrected peak around `Cp = 0.24` at `lambda = 4.0`. (source: sources/va23.md)
- The source says this case underperforms the `50% STS-VAWT` near peak power because the smaller blades generate less power despite reduced blade-wake interaction. (source: sources/va23.md)
- At `700 rpm`, the paper says the `100% STS-VAWT` outperforms the conventional VAWT across the tested TSR range, but still trails the `50%` shifted case over most of the useful range. (source: sources/va23.md)

## Related

- [[Blade-Wake Interaction]]
- [[Wind Tunnel Blockage Correction]]
- [[va23 Shifted Troposkien Vertical Offset]]

#designs
