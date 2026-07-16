---
Created: 2026-07-15
Updated: 2026-07-16
Sources:
  - "[[HRI2526]]"
  - "[[cj4]]"
  - "[[cj5]]"
  - "[[cj6]]"
  - "[[cj7]]"
  - "[[cj8]]"
Source_count: 6
tags:
  - methods
---
## SimScale

Browser-based simulation platform used in this repo's sources for VAWT CFD workflow setup and early design testing. (source: sources/HRI2526.md, sources/cj4.md)

- The HRI report uses SimScale with an inner rotating domain and an outer stationary domain to predict `Cp` and study operating conditions for selected VAWT designs. (source: sources/HRI2526.md)
- The same report says `k-omega SST` was used for all of its simulations and that validation against simpler reference cases was necessary before trusting more complex turbine studies. (source: sources/HRI2526.md)
- The `cj4` tutorial adds a beginner-oriented quick-start workflow: import CAD, create the outer flow volume, use boolean subtraction to obtain the fluid region, choose incompressible air flow, and set inlet velocity plus outlet pressure. (source: sources/cj4.md)
- The tutorial also uses cutting planes, pressure contours, forces/moments, and particle tracing for interpretation and troubleshooting. (source: sources/cj4.md)
- The `cj5` tutorial adds a generic external-flow version of that workflow, with a velocity inlet, pressure outlet, slip-wall side boundaries, and explicit setup of a `forces and moments` result control on the solid surfaces. (source: sources/cj5.md)
- It also gives a practical reading rule for quick studies: use the stabilized end of the force-history plot rather than the noisy startup portion when estimating the reported load value. (source: sources/cj5.md)
- The `cj6` tutorial adds a building-wind example that emphasizes keeping enough top head space in the domain to capture accelerated flow and choosing the inlet direction and speed from local wind data rather than from an arbitrary guess. (source: sources/cj6.md)
- In that example, the outer box uses a velocity inlet on one face, pressure outlets on the other exposed faces, and wall geometry for the ground and building surfaces. (source: sources/cj6.md)
- The `cj7` documentation adds a more detailed rotating-zone workflow: use a flow region with removed solids plus a cylinder around the rotating part, define symmetry planes where possible, assign an `MRF rotating zone`, and let physics-based meshing create the needed cell zones automatically. (source: sources/cj7.md)
- It also documents a custom atmospheric boundary using `Pressure inlet-outlet velocity` with total gauge pressure `0 Pa`, plus post-processing through pressure coloring, particle traces, and cutting-plane vectors. (source: sources/cj7.md)
- The `cj8` forum troubleshooting note adds two practical support checks: coefficient outputs can be badly wrong if reference area, velocity, or density are mis-set, and boundary-layer inflation can fail if tiny near-wall layers transition too abruptly into much larger surface cells. (source: sources/cj8.md)
- The same forum note also says rotating-zone failures in incompressible cases often come from a rotating volume that does not intersect a material-assigned fluid region correctly. (source: sources/cj8.md)
- The HRI report adds an important caution that default physics-based meshing can be expedient, but unresolved boundary-layer treatment can limit confidence in the result. (source: sources/HRI2526.md)

> Uncertainty: these sources support SimScale as a practical learning and early-analysis tool, but they do not establish one universally correct SimScale recipe for VAWTs. `cj4`, `cj5`, and `cj6` are quick tutorials, `cj7` is a drone-oriented rotating-zone example, `cj8` is forum troubleshooting guidance, and `HRI2526` explicitly notes unresolved meshing limitations in part of its validation path. (source: sources/HRI2526.md, sources/cj4.md, sources/cj5.md, sources/cj6.md, sources/cj7.md, sources/cj8.md)

Related: [[CFD]], [[cj4 SimScale Savonius Workflow]], [[cj5 SimScale Virtual Wind Tunnel Workflow]], [[cj6 SimScale Building Wind Workflow]], [[cj7 SimScale MRF Rotating Zone Workflow]], [[cj8 SimScale Forum Troubleshooting Notes]], [[HRI2526-summary]]

#methods
