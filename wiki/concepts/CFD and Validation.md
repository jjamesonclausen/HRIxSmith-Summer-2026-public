---
Created:
Updated: 2026-07-03
Sources:
- [[va10]]
- [[va9]]
- [[vj11]]
- [[vj2]]
- [[vj5]]
- [[vj6]]
Source_count: 6
Tags:
- concepts
---
## CFD and Validation

This page covers the simulation workflow used to check a VAWT before hardware is built.

- CFD is used to compare concepts, test geometry changes, and estimate torque and power coefficient. (source: sources/vj2.md, sources/vj5.md, sources/vj6.md)
- Mesh refinement matters. (source: sources/vj5.md, sources/vj6.md)
- The va10 review recommends explicit grid-independence and domain-size sensitivity checks before trusting performance outputs. (source: sources/va10.md)
- It says cells should be clustered near the blade and wake, with wall-adjacent resolution chosen to match the turbulence model's wall treatment. (source: sources/va10.md)
- PIV data is a useful validation target for VAWT CFD. (source: sources/vj5.md)
- The CFD review says 3-D models usually capture losses better than 2-D models. (source: sources/vj6.md)
- The review also uses torque, power coefficient, flow separation, and wake dynamics as key outputs. (source: sources/vj6.md)
- It reports that PISO outperformed SIMPLE and COUPLED in one reviewed Darrieus CFD comparison. (source: sources/va10.md)
- It also treats transition SST, LES, and hybrid RANS-LES as important when separation and unsteady wake fidelity matter more than design-stage speed. (source: sources/va10.md)

The VAWT review says URANS with `k-ω SST` is the main design-stage tool, while transition SST and DES/LES are preferred when dynamic stall fidelity matters most. (source: sources/vj11.md)
It reports that 2-D URANS can overpredict Cp by 15-30% relative to validated 3-D simulations. (source: sources/vj11.md)
It also recommends practical setup ranges of about 15D upstream, 10D downstream, 20D lateral extent, and 20-30 revolutions before sampling. (source: sources/vj11.md)

The va9 paper says its sliced DMS approach can be integrated into existing CFD and CAD tools to improve analysis of complex Darrieus blade-form designs. (source: sources/va9.md)
It also compares streamtube, vortex, and cascade models, noting that vortex models have high experimental correlation with the latest improvements but take the highest computation time among the listed prediction models. (source: sources/va9.md)

The hybrid-rotor CFD paper in `vj2` uses 3D SolidWorks Flow Simulation rather than 2D analysis because the authors say the vortex-like structures in the rotor require a full 3D domain. (source: sources/vj2.md)
It reports a computational domain of 15 m by 12 m by 12 m, 7 m/s inlet wind speed, 5% turbulence intensity, and torque samples at nine attack angles from 0 degrees to 120 degrees. (source: sources/vj2.md)

![Source figure](../../images/va10-fig5.jpg)
Original caption: Fig. 5. Computational grid independency study [31]. [[va10|Source]]

Related:
- [[Optimization]]
- [[Dynamic Stall]]
- [[Wind Tunnel Testing]]
- [[Double-Multiple Streamtube Model]]
