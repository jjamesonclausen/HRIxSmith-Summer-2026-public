---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj3]]"
Source_count: 1
tags:
  - summaries
---
## cj3 Summary

This source is a transcript of a YouTube course announcement for a `2D` Darrieus-VAWT CFD workflow in ANSYS Fluent, with an additional steady `3D` example included for learners. (source: sources/cj3.md)

- The transcript says the main worked case is a transient `2D` simulation with mesh motion, while the supplementary `3D` case uses a steady solution with frame motion. (source: sources/cj3.md)
- It says the course uses one reference paper to obtain turbine inputs such as airfoil profile, blade count, blade height, diameter, setting angle, wind speed, and Reynolds-number context, then uses `WebPlotDigitizer` to extract reference `Cp` data for comparison. (source: sources/cj3.md)
- The workflow described includes importing airfoil coordinates, building the blade arrangement, calculating a time step from turbine data, meshing with roughly `30` to `40` inflation layers in the `2D` case, and averaging torque over the last cycle. (source: sources/cj3.md)
- The speaker claims the demonstrated comparison reaches less than `1.38%` error after averaging the final cycle, but the transcript does not provide enough setup detail to independently reproduce or audit that result. (source: sources/cj3.md)

> Uncertainty: this is a promotional transcript rather than a full paper or full course note. It does not identify the reference paper by citation, does not provide the full Fluent settings, and only gives partial geometry and validation details. (source: sources/cj3.md)

Related pages: [[CFD]], [[CFD and Validation]], [[cj3 Darrieus Course CFD Workflow]], [[WebPlotDigitizer]]

#summaries
