---
Created: 2026-07-06
Source: "[[vj20]]"
tags:
  - designs
max Cp (1-4 m/s): 0.486
max Cp (4-8 m/s): 
max Cp (8-12 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 3
max TSR (4-8 m/s): 
max TSR (8-12 m/s): 
Swept area (m^2): 12.02448
Cut-in speed (m/s): 2.81
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 7.5
Rated power (W): 
---
## Proposed Hybrid VAWT

This page covers the source's proposed hybrid turbine that combines an outer straight-bladed H-rotor with an inner asymmetric-airfoil H-rotor instead of a Savonius starter. (source: sources/vj20.md)

![Source figure](vj20-fig1.jpg)
Original caption: Figure 1. Conceptual model and operating principle of the hybrid wind turbine under consideration. Wind's kinetic energy is transformed into electricity using a hybrid vertical axis wind turbine (VAWT) with asymmetric (inner side) and symmetric (outer side) airfoil blades that can be employed via an energy storage device. [[vj20|Source]]

## Geometry

- The full-scale outer turbine uses three `NACA0018` blades with `3.854 m` rotor diameter, `3.120 m` rotor height, `0.546 m` chord length, and `-2.82` degree pitch angle. (source: sources/vj20.md)
- The full-scale inner turbine uses three `DU 06-W-200` blades with `1.578 m` rotor diameter, `1.605 m` rotor height, `0.547 m` chord length, and `-3.41` degree pitch angle. (source: sources/vj20.md)
- The inner turbine is mounted `60` degrees from the outer turbine, while the three outer blades are spaced `120` degrees apart. (source: sources/vj20.md)
- The paper presents the whole system as a connected dual-rotor arrangement on a central shaft with connecting rods, joints, bearings, generator, and battery storage. (source: sources/vj20.md)

![Source figure](vj20-fig2.jpg)
Original caption: Figure 2. Computer-aided design (CAD) of a scaled-down model of the proposed design. The dimensions with small letters represent the scaled-down model. [[vj20|Source]]

## Performance

- The proposed hybrid reports peak `Cp = 0.486` at `TSR = 3` and exceeds the compared H-rotor Darrieus (`Cp = 0.42`) and cited existing hybrid (`Cp = 0.41`). (source: sources/vj20.md)
- It reports peak `Ct = 0.324` at `TSR = 3`. (source: sources/vj20.md)
- The source says positive `Cts` at all azimuths show complete self-starting, with maximum `Cts` values of `0.269`, `0.309`, and `0.291` at `3`, `3.64`, and `5 m/s` respectively. (source: sources/vj20.md)
- The paper states that the design improves performance by about `11%-13%` over the compared H-rotor Darrieus and existing hybrid configurations. (source: sources/vj20.md)

## Source-specific notes

- The similarity table gives whole-turbine full-scale values of rated wind speed `7.5 m/s`, cut-in speed `2.81 m/s`, and `Cp = 0.491`. (source: sources/vj20.md)
- The later experimental/comparison sections also report scaled-model cut-in-style values of `1.72 m/s` and `1.54 m/s`, so the source contains multiple context-dependent startup numbers. (source: sources/vj20.md)

> Discrepancy: the frontmatter uses the full-scale similarity-table cut-in and rated-speed values, but the paper also reports scaled-model startup values in the experimental and comparison sections. The rated power field is left blank because the paper only gives a scaled-model `1.4 W` comparison point rather than one source-clear full-scale rated power. (source: sources/vj20.md)

Related: [[Hybrid VAWT]], [[H-VAWT]], [[Scaling Effects]], [[vj20 Blade Surface Roughness]], [[Box-Behnken Design]]

#designs
