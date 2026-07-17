---
Created: 2026-07-17
Updated: 2026-07-17
Sources:
  - "[[ca37]]"
Source_count: 1
tags:
  - CFD
---
# ca37 NACA 2412 Airfoil Validation

## Scope

This source reports a steady, two-dimensional external-flow validation of a `230 mm`-chord NACA 2412 airfoil at `30 m/s`, `Re = 4.4 x 10^5`, and angles of attack from `0 degrees` to `16 degrees`. (source: sources/ca37.md)

## Reported setup

- The authors used a C-type two-frame domain with far-field enclosure dimension `10C`, divided the airfoil surface into `320` segments, and report an unstructured `70,000-80,000`-cell mesh with fine airfoil-wall refinement. (source: sources/ca37.md)
- Air density was `1.225 kg/m^3`, dynamic viscosity was `1.7894 x 10^-5 kg/(m s)`, gauge pressure was `0 Pa`, and operating pressure was `101325 Pa`. (source: sources/ca37.md)
- The calculation used steady incompressible RANS with pressure-velocity coupling through SIMPLE and first-order upwind discretisation. The paper compares Spalart-Allmaras, realizable `k-epsilon`, and `k-omega SST`; it states turbulence was maintained at `1%-5%`. (source: sources/ca37.md)

![Source figure](../../images/ca37-fig1.jpg)
Original caption: Fig. 1. a) C- Topology fine mesh and no slip far field view b) Flow separation behavior. [[ca37|Source]]

## Reported validation outcome

- The paper reports that Spalart-Allmaras best followed its selected NACA 2412 experimental comparison, with least reported error `6.04%`; it reports a maximum `19%` error at `14 degrees` angle of attack. (source: sources/ca37.md)
- It reports lift increasing through `14 degrees` and then decreasing by `22%`, and describes flow detachment before `0.25C` after the stated critical angle. (source: sources/ca37.md)
- The paper says the realizable `k-epsilon` and `k-omega` models became inaccurate as angle of attack increased in this specific comparison. (source: sources/ca37.md)

![Source figure](../../images/ca37-fig3.jpg)
Original caption: Fig. 1 Lift to AOA curves showing the variation between the turbulence models to the experimental model. [[ca37|Source]]

> Uncertainty: This is one reported steady, two-dimensional validation case. The paper does not report residual criteria, solved `y+`, a grid-independence study, or the full experimental data and error calculation, so its turbulence-model ranking should not be transferred directly to a different airfoil, Reynolds number, transition condition, or rotating VAWT flow. (source: sources/ca37.md)

Related pages: [[CFD]], [[CFD and Validation]], [[Airfoil Selection for Small Straight-Bladed VAWTs]].

#CFD
