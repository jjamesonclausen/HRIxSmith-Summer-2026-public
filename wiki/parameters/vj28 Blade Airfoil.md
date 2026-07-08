---
Created: 2026-07-08
Source: [[vj28]]
Tags: #parameters
Target: improve self-starting and aerodynamic performance
Outcome: significant positive effect
---
## Blade Airfoil

This `vj28` paper treats blade airfoil choice as the main design variable for improving smaller-capacity fixed-pitch straight-bladed Darrieus / SB-VAWT rotors. (source: sources/vj28.md)

## Parameter

- The paper frames the conventional symmetric `NACA 0012`, `0015`, and `0018` sections as the old default baseline used in many earlier SB-VAWT designs. (source: sources/vj28.md)
- It screens five public-domain asymmetric candidates against that baseline: `GOE 420`, `NACA 4415`, `LS(1)-0417`, `NLF(1)-0416`, and `S1210`. (source: sources/vj28.md)
- The desired aerodynamic traits are large low-Re stall angle, wide drag bucket, low zero-lift drag, high `Cl/Cd`, high `Cl,max`, delayed deep stall, low roughness sensitivity, low trailing-edge noise, and large negative pitching moment. (source: sources/vj28.md)
- The desired geometric traits are camber, greater thickness, large leading-edge radius, and sharp trailing edge. (source: sources/vj28.md)

## Outcome

- The paper concludes that a high-lift, low-drag asymmetric thick airfoil is preferable to the older symmetric `NACA` sections for this application. (source: sources/vj28.md)
- Among the screened candidates, `S1210` gives the strongest reported positive-incidence tangential-force behavior and several of the strongest positive-incidence lift-related metrics, while `NLF(1)-0416` gives the widest low-Re drag bucket, `LS(1)-0417` is least roughness-sensitive in `Cdo`, and `NACA 4415` is the quietest in the `NAFNoise` comparison. (source: sources/vj28.md)
- The source therefore treats airfoil selection as a multi-criteria tradeoff rather than a single-metric ranking problem. (source: sources/vj28.md)

![Source figure](vj28-fig22.jpg)
Original caption: Figure 22. Geometric Features of a Typical Asymmetric Airfoil [[vj28|Source]]

> Uncertainty: the paper explicitly says none of the candidate airfoils has all the desired characteristics, several dedicated VAWT airfoils could not be fully evaluated, and parts of the comparison depend on `XFOIL` plus extrapolated post-stall data. (source: sources/vj28.md)

#parameters
