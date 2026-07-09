---
Created: 2026-07-03
Updated: 2026-07-07
Sources:
  - "[[va12]]"
Source_count: 1
tags:
  - methods
---
## 3D Particle Tracking Velocimetry

Volumetric flow-measurement method that reconstructs three-dimensional particle trajectories from multiple synchronized camera views. (source: sources/va12.md)

![Source figure](va12-fig1.jpg)
Original caption: Figure 1. (a) Side-view and (b) top view of the wind tunnel test section with the two turbine array shown. In both views. the filled black rectangles represent the fan grid and the dashed black rectangles represent the maximum extent of the particle tracking measurement domain. The red dots illustrate the configuration of the seven-camera setup above the wind tunnel. All cameras were installed at the same height above the tunnel, and were oriented such that the turbine pair was in the center of the frame. (c) Illustration of the two turbine array geometry and the coordinate system used in the wind tunnel. Turbine 1 (T1) was defined as the upstream turbine and is located at a fixed position at (X, Y, Z) = (0, 0, 0). Turbine 2 (T2) is the downstream turbine and could be located at angles (phi) with respect to the freestream (U) within -90 degrees <= phi <= 90 degrees and turbine spacings (s) within 1.25 D <= s <= 3 D. Both turbines could be oriented to rotate either clockwise or counter-clockwise. [[va12|Source]]
![Source figure](va12-fig2.jpg)
Original caption: Figure 2. (a) Distribution of number of vectors per (2 cm)^3 voxel in the freestream measurement with an empty test section. (b) Standard deviation of the means of Uo calculated from 2000 re-samplings of data (sigma_rs/Uo) versus the number of vectors used in the re-sampling. Data are from the voxel with the most vectors in the freestream measurement. [[va12|Source]]

- The source uses seven synchronized cameras above the tunnel with neutrally buoyant helium-filled soap-bubble tracers. (source: sources/va12.md)
- Particles were triangulated only when they appeared in at least three camera views, then tracked across frames to recover velocity. (source: sources/va12.md)
- Mean velocity fields were voxel-averaged in 2 cm cubed cells, and vorticity was computed by differentiating the time-averaged velocity field. (source: sources/va12.md)
- The paper uses 3D-PTV specifically because planar methods miss important three-dimensional interactions between paired VAWT wakes. (source: sources/va12.md)

Related:
- [[PIV Testing]]
- [[Wind Tunnel Testing]]
- [[H-rotor Wake Aerodynamics]]

#methods
