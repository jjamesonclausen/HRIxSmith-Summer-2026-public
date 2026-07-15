---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[HRI2526]]"
  - "[[cj4]]"
Source_count: 2
tags:
  - methods
---
## SimScale

Browser-based simulation platform used in this repo's sources for VAWT CFD workflow setup and early design testing. (source: sources/HRI2526.md, sources/cj4.md)

- The HRI report uses SimScale with an inner rotating domain and an outer stationary domain to predict `Cp` and study operating conditions for selected VAWT designs. (source: sources/HRI2526.md)
- The same report says `k-omega SST` was used for all of its simulations and that validation against simpler reference cases was necessary before trusting more complex turbine studies. (source: sources/HRI2526.md)
- The `cj4` tutorial adds a beginner-oriented quick-start workflow: import CAD, create the outer flow volume, use boolean subtraction to obtain the fluid region, choose incompressible air flow, and set inlet velocity plus outlet pressure. (source: sources/cj4.md)
- The tutorial also uses cutting planes, pressure contours, forces/moments, and particle tracing for interpretation and troubleshooting. (source: sources/cj4.md)
- The HRI report adds an important caution that default physics-based meshing can be expedient, but unresolved boundary-layer treatment can limit confidence in the result. (source: sources/HRI2526.md)

> Uncertainty: the two sources support SimScale as a practical learning and early-analysis tool, but they do not establish one universally correct SimScale recipe for VAWTs. `cj4` is only a quick tutorial transcript, and `HRI2526` explicitly notes unresolved meshing limitations in part of its validation path. (source: sources/HRI2526.md, sources/cj4.md)

Related: [[CFD]], [[cj4 SimScale Savonius Workflow]], [[HRI2526-summary]]

#methods
