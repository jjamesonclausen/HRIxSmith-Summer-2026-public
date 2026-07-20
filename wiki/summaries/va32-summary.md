---
Created: 2026-07-20
Updated: 2026-07-20
Sources:
  - "[[va32]]"
Source_count: 1
tags:
  - summaries
---
# va32 Summary

This paper derives computational-setting guidance for 2D URANS simulations of a two-bladed H-type VAWT, using a sensitivity study over tip-speed ratio, solidity, time resolution, domain length, and revolutions to convergence. (source: sources/va32.md)

![Reference turbine, domain, and grid.](../../images/va32-fig1.jpg)
Original caption: Fig. 1. Schematic of the turbine for the reference case (not to scale). [[va32|Source]]

Key points:
- The reference rotor has two NACA0018 blades, `D = 1 m`, `c = 0.06 m`, solidity `0.12`, and a `0.04 m` shaft; it operates at `U_infinity = 9.3 m/s`, `TSR = 4.5`, `Omega = 83.8 rad/s`, and `5%` freestream turbulence intensity. (source: sources/va32.md)
- The tested model uses 2D URANS with transition SST, a sliding rotating core of `1.5D`, `~400,000` quadrilateral cells, and average/max blade `y+` of `1.37/4`. (source: sources/va32.md)
- For the studied low-solidity rotor, `0.1 degrees` azimuthal increment is required at low-to-moderate `TSR` (`1.5-3.5`), while `0.5 degrees` is sufficient at moderate-to-high `TSR` (`>3.5`). Low chord Reynolds number (`Re_c < 10^5`) also requires the finer increment. (source: sources/va32.md)
- To limit the isolated influence of domain boundaries on predicted `Cp` to below `1%`, the paper finds a minimum center-to-inlet distance of `15D`, center-to-outlet distance of `10D`, and domain width of `20D`. (source: sources/va32.md)
- Sampling should begin after `20-30` turbine revolutions in the studied URANS cases; this is not a general convergence proof for a different turbine, model, mesh, or scale-resolving method. (source: sources/va32.md)

Related pages: [[va32 Reference H-Type VAWT]], [[va32 VAWT URANS Computational Guidelines]], [[SimScale VAWT CFD Learning Path]], [[CFD]].
