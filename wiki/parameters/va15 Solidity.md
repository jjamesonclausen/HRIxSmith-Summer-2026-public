---
Created: 2026-07-03
Source: [[va15]]
Tags: #parameters
Target: improve self-starting
Outcome: significant positive effect
---
## Solidity

The `va15` study treats turbine solidity as a main startup and performance variable for a 3-bladed H-Darrieus rotor. (source: sources/va15.md)

## Parameter

- The paper tests three solidities: `sigma = 0.67`, `sigma = 0.81`, and `sigma = 1.0`. (source: sources/va15.md)
- Solidity is changed by modifying turbine radius while keeping blade number and chord fixed. (source: sources/va15.md)

![Source figure](va15-fig4.jpg)
Original caption: FIGURE 4 Schematic drawing of turbine configurations for different solidities [[va15|Source]]

## Outcome

- High solidity (`sigma >= 0.81`) improves self-starting because increased blockage helps generate startup torque. (source: sources/va15.md)
- The source reports startup for `sigma = 1.0` and `sigma = 0.81`, but failure to self-start for `sigma = 0.67`. (source: sources/va15.md)
- The paper also reports that the maximum `Cp` of the `sigma = 0.81` case shifts toward about `lambda = 2.0`, reinforcing that lower solidity can help peak performance once startup is no longer the limiting issue. (source: sources/va15.md)
- That startup gain comes at the expense of lower peak power output, so the source frames solidity as a blockage-versus-peak-`Cp` tradeoff. (source: sources/va15.md)

## Related

- [[Wind Turbine Parameters]]
- [[va15 Blade Profile]]
- [[va15 Blade Pitch Angle]]

#parameters
