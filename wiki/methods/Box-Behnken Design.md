---
Created: 2026-07-06
Updated: 2026-07-07
Sources:
  - "[[vj20]]"
Source_count: 1
tags:
  - methods
---
## Box-Behnken Design

DOE method used to optimize several design variables at once with fewer runs than a full factorial design. (source: sources/vj20.md)

- The `vj20` paper uses Box-Behnken to optimize chord length, number of blades, distance from the central rotating shaft, pitch angle, and rotor height. (source: sources/vj20.md)
- The source says each independent variable is set at one of three equally spaced levels: maximum, average, and minimum. (source: sources/vj20.md)
- It reports `46` runs for the five-variable investigation. (source: sources/vj20.md)
- The workflow is paired with response surface methodology and a regression model in Minitab to evaluate the effects on `Cp` and cut-in speed. (source: sources/vj20.md)
- The paper frames Box-Behnken as a more efficient screening approach than full factorial while still supporting response-surface fitting and optimization. (source: sources/vj20.md)

Related: [[Optimization]], [[CFD]], [[Scaling Effects]], [[vj20-summary]]

#methods
