---
Created: 2026-07-03
Source: "[[va15]]"
tags:
  - parameters
Target: improve self-starting
Outcome: significant positive effect
---
## Blade Aspect Ratio

The `va15` study compares two blade spans, keeping chord fixed, to test how aspect ratio affects self-starting. (source: sources/va15.md)

## Parameter

- The tested aspect ratios are `AR = 7` and `AR = 6`, obtained from blade spans of 700 mm and 600 mm with the same 100 mm chord. (source: sources/va15.md)

![Source figure](va15-fig20.jpg)
Original caption: FIGURE 20 Self-starting time-varying results for turbine with different blade aspect ratios at sigma = 1.0 [[va15|Source]]

## Outcome

- Reducing blade span by 14% from 700 mm to 600 mm caused the tested turbine to fail to self-start. (source: sources/va15.md)
- The `AR = 6` case only reaches about `lambda = 0.85`, which the paper treats as insufficient for sustained self-starting. (source: sources/va15.md)
- The paper also notes that this failure to self-start persists across the tested solidity range and remains a concern even when other profile choices are considered. (source: sources/va15.md)
- The paper concludes that larger blade span, and therefore larger aspect ratio, helps self-starting by reducing tip-loss effects and increasing the margin between aerodynamic torque and system resistance. (source: sources/va15.md)
- This result is stricter than some prior thresholds cited by the authors, so the paper effectively argues that `AR > 5.7` alone is not a sufficient self-start guarantee. (source: sources/va15.md)

## Related

- [[H-VAWT]]
- [[Wind Turbine Parameters]]

#parameters
