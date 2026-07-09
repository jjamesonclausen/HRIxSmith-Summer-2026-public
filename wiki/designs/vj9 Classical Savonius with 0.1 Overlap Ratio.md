---
Created: 2026-07-03
Source: "[[vj9]]"
tags:
  - designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
max Cp (8-12 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
max TSR (8-12 m/s): 
Swept area (m^2): 
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## Classical Savonius with 0.1 Overlap Ratio

The `vj9` source uses a classical two-bladed Savonius rotor with overlap ratio `s/d = 0.1` as its reference design for CFD validation and comparison against modified blade shapes. (source: sources/vj9.md)

## Geometry

- The baseline design is a Savonius-type VAWT with blade overlap defined as `s/d = 0.1`. (source: sources/vj9.md)
- The source uses circular end plates with diameter about 10% larger than rotor diameter (`dep = 1.1d`). (source: sources/vj9.md)
- The optimization and validation work is centered near TSR 0.9 and wind speed 12 m/s. (source: sources/vj9.md)

![Source figure](vj9-fig1.jpg)
Original caption: Figure 1: Schematic of Savonius-type VAWT. [[vj9|Source]]

## Unique Design Choices

- The paper treats this as the classical reference case against which modified Bach-like, scooplet-based, spline, elliptical, and other designs are compared. (source: sources/vj9.md)

## Performance

- The source says moderate overlap ratios around `0.1-0.15` improve peak power coefficient relative to zero overlap. (source: sources/vj9.md)
- The classical `s/d = 0.1` rotor is used as the reference design for the reported 39% improvement of the scooplet-based design. (source: sources/vj9.md)

## Related

- [[vj9 Modified Classical Savonius]]
- [[vj9 Scooplet-Based Savonius]]
- [[vj9 Savonius Blade Shape]]

#designs
