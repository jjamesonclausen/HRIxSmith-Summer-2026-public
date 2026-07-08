---
Created: 2026-07-03
Source: [[vj8]]
Tags: #parameters
Target: reduce total torque
Outcome: significant positive effect
---
## Included Angle Between Rotors

This `vj8` study changes the included angle between the upper and lower rotors of the CRVAWT to improve stability by reducing total torque. (source: sources/vj8.md)

## Parameter Change

- The study simulates included angles from `0°` to `180°` in `30°` steps. (source: sources/vj8.md)

![Source figure](vj8-fig16.jpg)
Original caption: Fig. 16. The variation of torque and time of CRVAWT under different included angles. [[vj8|Source]]

## Outcome

- The source says upper-rotor torque is nearly unchanged across included angles, but total torque changes strongly. (source: sources/vj8.md)
- At `90°`, the total-torque peak exceeds the peak torque of the upper rotor alone, showing that rotor interaction can amplify combined response rather than only cancel it. (source: sources/vj8.md)
- At `θ = 0°`, the total torque is close to zero, which the paper says makes platform-stability impact almost negligible. (source: sources/vj8.md)
- The response-surface optimum also selects `0°` included angle, which means the practical design recommendation is driven by platform-stability needs rather than by maximizing raw combined torque. (source: sources/vj8.md)

#parameters
