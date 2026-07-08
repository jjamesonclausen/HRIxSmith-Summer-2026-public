---
Created: 2026-07-06
Source: [[vj24]]
Tags: #parameters
Target: increase power output
Outcome: significant positive effect
---
## Blade Airfoil

This `vj24` paper treats blade airfoil redesign as the main design variable for improving a low-speed straight-bladed Darrieus rotor. (source: sources/vj24.md)

## Parameter

- The baseline blade section is `NACA 0018`. (source: sources/vj24.md)
- The airfoil is redesigned into a modified symmetric section, `NACA 0018-M`, using an inverse-design workflow that adjusts the upper- and lower-surface `alpha*` / velocity-distribution targets while keeping practical constraints such as `18%` thickness-to-chord ratio and zero pitching moment. (source: sources/vj24.md)
- The design strategy focuses on changing the transition-ramp behavior and reducing undesirable low-Re flow features such as laminar separation bubbles. (source: sources/vj24.md)

## Outcome

- The paper reports that the modified airfoil raises the example turbine's predicted power from `1.610 kW` to `1.850 kW`. (source: sources/vj24.md)
- It also reports `CP` increasing from `0.294` to `0.338` and `CQ` increasing from `0.184` to `0.211`. (source: sources/vj24.md)
- The source frames this as meeting the intended `10-15%` relative improvement target for a small VAWT at `TSR = 1.6`. (source: sources/vj24.md)
- Qualitatively, the final design is reported to delay transition, improve lift-curve behavior, and reduce drag at `alpha > 15 deg`, even though it has slightly higher drag at low angles of attack. (source: sources/vj24.md)

![Source figure](vj24-fig2.jpg)
Original caption: Figure 2: Comparison of aerodynamic and boundary layer characteristics of the original NACA 0018 airfoil and the final design NACA 0018-M airfoil with experiments [9]. [[vj24|Source]]

![Source figure](vj24-fig4.jpg)
Original caption: Figure 4: Comparison of surface pressure coefficient distribution at Re = 200000 and alpha = 0 deg. [[vj24|Source]]

> Uncertainty: the source explicitly says the improvement should be interpreted qualitatively and relatively, because XFOIL remains weak for low-Re high-angle-of-attack post-stall prediction. (source: sources/vj24.md)

#parameters
