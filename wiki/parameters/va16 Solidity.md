---
Created: 2026-07-03
Source: [[va16]]
Tags: #parameters
Target: increase Cp
Outcome: significant positive effect
---

## Solidity

The `va16` study evaluates solidity through chord and span changes to understand how it alters power coefficient in a straight-bladed VAWT. (source: sources/va16.md)

## Parameter

- At fixed `H/c = 6`, the tested cases include `H/D = 0.6`, `0.9`, and `1.2`, with corresponding solidity changes. (source: sources/va16.md)
- The paper explicitly compares fixed-solidity and fixed-rotor-aspect-ratio cases to separate the roles of solidity and `H/D`. (source: sources/va16.md)

![Source figure](../../images/va16-fig9.jpg)
Original caption: Fig. 9. Fluctuation of power coefficient curve against the tip speed ratio lambda in the case of the fixed aspect ratio. [[va16|Source]]

## Outcome

- At fixed `H/c = 6`, the paper says power coefficient depends on rotor aspect ratio through solidity rather than on `H/D` alone. (source: sources/va16.md)
- The paper therefore treats solidity as the stronger driver than `H/D` when `H/c` is fixed. (source: sources/va16.md)
- Higher solidity shifts the optimum tip-speed ratio to lower values in the reported fixed-`H/c` comparison. (source: sources/va16.md)
- The source also notes that lower-`H/D` / higher-solidity cases can produce unfavorable bound-circulation behavior near the blade tip, especially around `H/D = 0.9` relative to `1.2`. (source: sources/va16.md)
- This is a numerical study, so the outcome is a simulation-based trend rather than a direct experimental validation. (source: sources/va16.md)

## Related

- [[Wind Turbine Parameters]]
- [[va16 Span-to-Diameter Ratio (H-D)]]

#parameters
