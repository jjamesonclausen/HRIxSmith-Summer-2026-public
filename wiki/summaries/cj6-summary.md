---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj6]]"
Source_count: 1
tags:
  - summaries
---
## cj6 Summary

This source is a SimScale tutorial for simple building-scale wind simulation, focused on setting up a surrounding air volume, assigning inlet and outlet faces, and choosing a representative inlet wind direction and speed. (source: sources/cj6.md)

- The tutorial builds a simplified building inside a larger air box, then uses solid subtraction so the simulation geometry represents the surrounding air region. (source: sources/cj6.md)
- It emphasizes leaving substantial head space above the object because wind acceleration over the top can otherwise be missed if the box is too short. (source: sources/cj6.md)
- The setup uses incompressible air, one velocity-inlet face, pressure outlets on the remaining outer faces, and wall geometry for the ground plane and building. (source: sources/cj6.md)
- The inlet speed is selected from local wind data, with the example using a winter average value of `6.26` based on a wind-rose workflow and seasonal climate reasoning. (source: sources/cj6.md)

> Uncertainty: this is a simple building-wind tutorial, not a validated turbine or urban-CFD study. It does not report turbulence model, mesh settings, or benchmark comparison data. (source: sources/cj6.md)

Related pages: [[CFD]], [[cj6 SimScale Building Wind Workflow]], [[SimScale]], [[SimScale VAWT Domain and Boundaries]]

#summaries
