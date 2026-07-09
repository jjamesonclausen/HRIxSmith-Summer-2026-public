---
Created: 2026-07-08
Updated: 2026-07-08
Sources:
  - "[[vj28]]"
Source_count: 1
tags:
  - methods
---
## NAFNoise

Airfoil-noise prediction program used to estimate trailing-edge noise from airfoil boundary-layer behavior. (source: sources/vj28.md)

- The `vj28` paper describes `NAFNoise` as an `NREL` airfoil-noise tool that predicts multiple airfoil self-noise sources, including trailing-edge noise. (source: sources/vj28.md)
- It says the program uses `XFOIL` boundary-layer calculations as inputs to empirical noise models originally developed by Brooks, Pope, and Marcolini. (source: sources/vj28.md)
- In the paper, `NAFNoise` is used to compare candidate SB-VAWT airfoils, and the reported result is that `NLF(1)-0416` generates the most noise while `NACA 4415` generates the least in the shown comparison. (source: sources/vj28.md)

![Source figure](vj28-fig19.jpg)
Original caption: Figure 19. Comparison of Sound Pressure Level (SPL) of Selected Prospective Airfoils [[vj28|Source]]

> Uncertainty: the noise comparison is model-based rather than a rotor-scale acoustic validation in a wind tunnel or field setup. (source: sources/vj28.md)

Related: [[XFOIL]], [[Airfoil Selection for Small Straight-Bladed VAWTs]], [[vj28-summary]]

#methods
