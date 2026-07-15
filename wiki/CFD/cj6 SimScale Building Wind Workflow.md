---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj6]]"
Source_count: 1
tags:
  - cfd
---
# cj6 SimScale Building Wind Workflow

## Setup outline

- The source demonstrates a simple SimScale wind-analysis workflow using a building-like object inside a larger surrounding air volume. (source: sources/cj6.md)
- It creates the air region by subtracting the inner solid from the outer box and exports that geometry into SimScale as the simulation object. (source: sources/cj6.md)
- The selected simulation type is incompressible flow with air assigned as the material. (source: sources/cj6.md)

## Domain and face assignment

- The tutorial warns that the top head space should be kept high enough to capture accelerated flow over the object. (source: sources/cj6.md)
- It assigns one outer face as the velocity inlet and the remaining exposed outer faces as pressure outlets. (source: sources/cj6.md)
- The ground plane and building surfaces are assigned as wall geometry in the setup. (source: sources/cj6.md)

## Inlet choice

- The example chooses inlet direction and speed from local wind data rather than from an arbitrary value. (source: sources/cj6.md)
- It specifically references wind-rose analysis and seasonal data selection, with a winter average velocity of `6.26` used for the shown setup. (source: sources/cj6.md)

> Uncertainty: the transcript is a simple environment-wind tutorial rather than a validated rotor or site-assessment study. It does not specify turbulence model, mesh strategy, or result-verification method, so it is best used as a setup example only. (source: sources/cj6.md)

Related pages: [[cj6-summary]], [[CFD]], [[SimScale]], [[SimScale VAWT Domain and Boundaries]]

#cfd
