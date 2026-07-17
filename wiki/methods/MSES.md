---
Created: 2026-07-17
Updated: 2026-07-17
Sources:
  - "[[ca36]]"
Source_count: 1
tags:
  - methods
---
# MSES

MSES is an Euler viscous-coupled airfoil-flow solver with a mixed-inverse design routine that can identify a geometry while solving for a specified pressure distribution. (source: sources/ca36.md)

- In this study, MSES supplied viscous seed-airfoil solutions, then the inverse routine changed upper and lower surfaces in stages until the viscous solution matched the target pressure distribution. (source: sources/ca36.md)
- The inverse iteration used inviscid analysis at the target freestream Mach number, with a fresh viscous solution after each geometry update to account for viscous decambering. (source: sources/ca36.md)
- MSES matched the overall measured pressure distributions at the measured operating points, but it underpredicted drag in the fixed-transition comparisons and did not reproduce all off-design natural-transition behavior. (source: sources/ca36.md)

> Uncertainty: the paper documents MSES at `M = 0.54` and Reynolds numbers near `1.27 x 10^6`; it does not establish MSES accuracy for a rotating VAWT blade, deep dynamic stall, or the much lower Reynolds numbers relevant to some VAWT cases. (source: sources/ca36.md)

Related: [[XFOIL]], [[ca36 Boundary-Layer-Informed Airfoil Design and Validation]], [[CFD and Validation]].
