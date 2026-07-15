---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj1]]"
Source_count: 1
tags:
  - cfd
---
# cj1 CFD Modelling and Validation

## Reusable CFD setup

- The study uses 2D ANSYS Fluent 2020 R1, a pressure-based solver, transient sliding-mesh motion, and `k-omega SST`. (source: sources/cj1.md)
- It sets inlet turbulence intensity to 2%, turbulence length scale to 3 m, outlet backflow turbulence intensity to 2.2, and outlet backflow turbulent-viscosity ratio to 0.1. (source: sources/cj1.md)
- The authors performed mesh sensitivity because they state that 2D predictions are grid/mesh sensitive. (source: sources/cj1.md)
- Their isolated-rotor geometry uses three NACA 7715 blades, 1 m chord, a 3 m rotor diameter, 5D inlet distance, 10D outlet distance, 10D domain width, and symmetry boundaries. (source: sources/cj1.md)
- They record torque at every time step and average it over one rotation. (source: sources/cj1.md)

![Figure 1: Computational domain and boundary conditions.](../../attachments/images/cj1-fig1.jpg)
Original caption: Fig. 1. (a) Computational domain; (b) Boundary conditions. [[cj1|Source]]

## Validation boundary

The paper compares experimental results only with CFD models of a matching isolated model at 12 m/s. The 200 mm-diameter experimental rotor has three NACA 7715 blades of 100 mm chord and 260 mm blade length. Its reported data uses torque-sensor measurements and the mean of five outlet-area anemometer readings. (source: sources/cj1.md)

The paper says the CFD trend underpredicts efficiency and does not reach a peak over the experimental TSR range. Therefore it supports trend-level validation of the isolated setup, not quantitative validation of the planetary cluster or of the reported optimum `Cp`. (source: sources/cj1.md)

## Planetary-case interpretation

At 6 m/s, the reported 30-degree arrangement at the stated 5-diameter center-to-center spacing gives the highest central-rotor `Cp` among the tested angles: `0.3405` at TSR `1.5`. The paper attributes this to the two upstream planet rotors altering the central blade pressure field. (source: sources/cj1.md)

![Figure 4: 30-degree planetary pressure and velocity fields.](../../attachments/images/cj1-fig4.jpg)
Original caption: Fig. 4. 30 degrees planetary turbine (U = 6 m/s, lambda = 1.5) (a) Pressure contours, (b) Velocity streamlines. [[cj1|Source]]

The result should not be generalized to all cluster layouts: the 0-, 60-, and 90-degree cases reduce peak central-rotor performance, and the 30-degree case performs worse than the isolated rotor at TSR `1.0` and `1.25`. (source: sources/cj1.md)

> Uncertainty: this is a 2D, single-paper result. The authors explicitly identify trailing vortices and tip losses as features 2D CFD cannot investigate, and do not report a planetary-cluster experiment. The document describes its optimum PCD as both `5D (3.75 m)` and a tested PCD of `3.75 m`; its own 3 m rotor diameter makes the `5D` label ambiguous. (source: sources/cj1.md)

Related pages: [[cj1-summary]], [[CFD]], [[CFD and Validation]]

#cfd
