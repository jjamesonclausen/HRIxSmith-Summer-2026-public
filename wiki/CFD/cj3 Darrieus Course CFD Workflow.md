---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj3]]"
Source_count: 1
tags:
  - cfd
---
# cj3 Darrieus Course CFD Workflow

## Stated workflow

- The source describes a teaching workflow for CFD analysis of a `2D` H-type Darrieus turbine in ANSYS Fluent, starting from airfoil coordinates and ending at torque and `Cp` comparison. (source: sources/cj3.md)
- It says the main case uses transient simulation with mesh motion, while the extra `3D` case is provided as a steady frame-motion setup rather than a transient `3D` solution. (source: sources/cj3.md)
- The transcript says the instructor takes turbine inputs from one reference paper, including airfoil profile, blade count, blade height, diameter, setting angle, wind speed, and Reynolds-number context. (source: sources/cj3.md)
- It also says `WebPlotDigitizer` is used to extract reference `Cp` data from the paper for one selected comparison condition. (source: sources/cj3.md)

## Geometry and mesh notes

- The source says airfoil coordinates are first reformatted for ANSYS, then used to create three airfoils at the required array positions and chord length. (source: sources/cj3.md)
- It says the `2D` setup uses three domains to simulate the flow and additional wake-focused regions because the wake is treated as important to the downstream flow properties. (source: sources/cj3.md)
- The transcript reports about `30` to `40` inflation layers around the airfoil in the `2D` mesh. (source: sources/cj3.md)

## Comparison method and limits

- The workflow includes a time-step calculation based on the real turbine data and post-processing of torque versus time step. (source: sources/cj3.md)
- The source says the last cycle is averaged for the final comparison and reports less than `1.38%` error for the demonstrated case. (source: sources/cj3.md)

> Uncertainty: this transcript is a course promotion, not the course itself. It does not fully specify the reference paper, domain dimensions, turbulence model, boundary conditions, or the exact comparison dataset, so it is useful as a workflow outline but not as a reproducible CFD recipe. (source: sources/cj3.md)

Related pages: [[cj3-summary]], [[CFD]], [[CFD and Validation]], [[WebPlotDigitizer]]

#cfd
