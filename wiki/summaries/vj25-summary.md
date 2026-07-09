---
Created: 2026-07-07
Updated: 2026-07-07
Sources:
  - "[[vj25]]"
Source_count: 1
tags:
  - summaries
---
## vj25 Summary

This paper studies how rotor aspect ratio changes the performance of a straight-bladed H-rotor VAWT, using a Multiple Stream Tube Model workflow and a `NACA 0018` two-bladed design example. (source: sources/vj25.md)

- The source defines aspect ratio as `AR = h/R`, where `h` is blade height and `R` is rotor radius. (source: sources/vj25.md)
- It argues that lowering `AR` increases rotor radius and chord for a fixed design power, which raises blade Reynolds number and improves the power coefficient. (source: sources/vj25.md)
- The paper also says lower `AR` reduces rotational speed while improving structural thickness and in-service stability because rotor inertia is larger. (source: sources/vj25.md)
- Its case study compares two `1 kW`, `2`-bladed, `NACA 0018` H-rotors at `10 m/s`: a converged `AR = 2` case with `cpmax = 0.464`, `R = 0.947 m`, `c = 0.189 m`, and `299 rpm`, and a converged `AR = 0.4` case with `cpmax = 0.475`, `R = 2.094 m`, `c = 0.314 m`, and `137 rpm`. (source: sources/vj25.md)
- The design loop is iterative: the paper starts from an assumed Reynolds number, reads `cpmax`, `sigma_cpmax`, and `lambda_cpmax` from MSTM-generated curves, resizes the rotor, recomputes Reynolds number, and repeats until the change is small. (source: sources/vj25.md)

![Source figure](vj25-fig6.jpg)
Original caption: Fig. 6 How aspect ratio influences Reynolds number and rotational velocity, for different design powers [[vj25|Source]]

![Source figure](vj25-fig8.jpg)
Original caption: Fig. 8 VAWT design flowchart [[vj25|Source]]

Related pages: [[Multiple Stream Tube Model]], [[H-VAWT]], [[Wind Turbine Parameters]], [[vj25 Rotor Aspect Ratio]], [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]], [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]]

#summaries
