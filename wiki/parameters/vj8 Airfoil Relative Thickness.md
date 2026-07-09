---
Created: 2026-07-03
Source: "[[vj8]]"
tags:
  - parameters
Target: balance Cp and manufacturability
Outcome: minimal positive effect
---
## Airfoil Relative Thickness

This `vj8` study changes the relative thickness of the CRVAWT blade airfoil to evaluate its effect on power coefficient and pressure distribution. (source: sources/vj8.md)

## Parameter Change

- The study compares NACA0015, NACA0018, NACA0021, and NACA0024 airfoils. (source: sources/vj8.md)

![Source figure](vj8-fig10.jpg)
Original caption: Fig. 10. Cross sections of four airfoils. [[vj8|Source]]

## Outcome

- The source says NACA0018 and NACA0021 show very similar power coefficients, while NACA0015 is the lowest-performing case. (source: sources/vj8.md)
- The reported average power coefficients are `0.1181`, `0.1362`, `0.1344`, and `0.1335` for NACA0015, NACA0018, NACA0021, and NACA0024 respectively. (source: sources/vj8.md)
- The source also reports pressure-difference comparisons of about `1014 Pa`, `890 Pa`, and `799 Pa` across key cases, which helps explain why a thinner profile can have stronger pressure difference but still lower net performance. (source: sources/vj8.md)
- The optimized relative thickness is `19.7%`, between NACA0018 and NACA0021, and the paper suggests NACA0020 as a practical balance between production cost and energy recovery efficiency. (source: sources/vj8.md)

#parameters
