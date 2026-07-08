---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[va25]]
Source_count: 1
Tags: #summaries
---
## va25 Summary

CFD airfoil-selection study for a straight-bladed H-Darrieus VAWT, focused on self-starting and low-TSR performance across symmetric, cambered-in, and cambered-out blade profiles. (source: sources/va25.md)

![Source figure](va25-fig19.jpg)
Original caption: Fig. 19 Max Cp and corresponding lambda for the studied airfoils with their different orientations. [[va25|Source]]
![Source figure](va25-fig18.jpg)
Original caption: Fig. 18 Startup analysis of cambered-out Clark Y and S1210. [[va25|Source]]

Key points:
- The paper evaluates a reference three-bladed straight-bladed Darrieus rotor and compares symmetric airfoils (`NACA0021`, `E474`, `S1048`) plus several cambered airfoils in both inward and flipped outward orientations. (source: sources/va25.md)
- For low TSR operation, cambered-in `NACA6712` performs best, reaching `Cp = 0.3645` at `TSR = 2.037` and about `180%` more `Cp` than the reference airfoil at the same TSR. (source: sources/va25.md)
- For mid-to-high TSR operation, symmetric `E474` performs best, with a maximum `Cp = 0.3557` at `TSR = 3.0` and about `19.5%` higher `Cp` than the reference at that TSR. (source: sources/va25.md)
- Flipping the camber outward significantly improves several weak cambered-in cases, with flipped `Clark Y` becoming the best of the cambered-out group and also showing the best startup behavior in the dynamic startup test. (source: sources/va25.md)
- The CFD setup uses `2D` URANS in ANSYS Fluent with SST `k-omega`, a sliding mesh, grid-independence analysis, and validation against published experimental data with less than `5%` maximum `Cp` error. (source: sources/va25.md)

Related concepts: [[H-VAWT]], [[Straight-bladed Darrieus]], [[CFD]], [[Dynamic Stall]], [[va25 Blade Airfoil Profile]], [[va25 Cambered Airfoil Orientation]]

#summaries
