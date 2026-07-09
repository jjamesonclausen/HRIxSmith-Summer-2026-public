---
Created: 2026-06-25
Updated: 2026-07-07
Sources:
  - "[[va1]]"
  - "[[vj19]]"
Source_count: 2
tags:
  - methods
---
## AEO Calculation

Method for estimating the annual energy output (AEO) of a wind turbine using wind distribution and power curves. (source: sources/va1.md)

- Wind speed distribution is divided into bins (e.g., 1 m/s intervals). (source: sources/va1.md)
- For each bin:
  - Determine probability of wind speed occurrence. (source: sources/va1.md)
  - Multiply by total annual hours (8760 h). (source: sources/va1.md)
  - Multiply by turbine power output at that wind speed (from power curve). (source: sources/va1.md)
- Sum contributions across all bins to obtain total AEO. (source: sources/va1.md)
- The vj19 study gives a concrete bin-table version of the same workflow: use annual hour counts and Rayleigh probabilities for each wind-speed bin, multiply by simulated electrical power at that speed, and sum the per-bin energies to estimate yearly output. (source: sources/vj19.md)

> Inference: Accuracy depends heavily on quality of wind data and validity of the turbine power curve.

Related: [[Bin Method]], [[Annual Energy Output]]

#methods
