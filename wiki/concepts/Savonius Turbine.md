---
Created: 2026-06-25
Updated: 2026-07-07
Sources:
  - "[[HRI2526]]"
  - "[[vj12]]"
  - "[[vj13]]"
  - "[[vj17]]"
  - "[[vj19]]"
  - "[[n1]]"
  - "[[vj11]]"
  - "[[va8]]"
  - "[[va3]]"
  - "[[va5]]"
  - "[[vj27]]"
  - "[[vj26]]"
  - "[[n2]]"
  - "[[vj2]]"
  - "[[va29]]"
  - "[[va30]]"
Source_count: 16
tags:
  - concepts
---
## Savonius Turbine

Drag-based VAWT using scooped blades. (source: sources/n1.md, sources/va1.md)

![Source figure](vj2-fig1.jpg)
Original caption: Figure 1: Basic design of a Savonius rotor [[vj2|Source]]

- Geometry:
  - Typically uses two semicircular blades around a vertical shaft. (source: sources/HRI2526.md)
  - Classical and helical forms are both represented in the wiki. (source: sources/HRI2526.md)
- Performance:
  - Self-starting and effective at low wind speeds. (source: sources/HRI2526.md)
  - TSR is typically between 0 and 1. (source: sources/HRI2526.md)
- The review says overlap ratio has no single optimum, but 0.1-0.15 is a common useful range and no-overlap cases can still win on mechanical power in some studies. (source: sources/vj12.md)
- It reports that inner blades can raise Cp by up to 41%, with different gap settings favoring one- or two-inner-blade layouts. (source: sources/vj12.md)
- It says some twisted Savonius designs improve Cp substantially, including a 180-degree twist case that improved Cp by 51%. (source: sources/vj12.md)
- The vj13 cluster study uses a conventional two-blade Savonius rotor with overlap ratio `0.1`, `D = 0.95 m`, and `H = 1 m` as the base turbine for a three-rotor cluster. (source: sources/vj13.md)
- It reports a validated isolated-turbine maximum Cp of about `0.3372` at `7 m/s` and shows that cluster output is dominated by wind-direction wake interaction. (source: sources/vj13.md)
- The vj17 optimization study adds an airfoil-based Savonius variant that raises Cp by about 27% over a semicircular baseline when optimized with DVM, CST, and SSA. (source: sources/vj17.md)
- The vj19 experimental-modeling study uses a three-blade Savonius layout and reports that straight blades gave the lowest RPM, twisted blades the highest RPM, and curved blades nearly matched twisted performance before being selected for the later system study. (source: sources/vj19.md)
- Tradeoffs:
  - Simple, low-cost construction and low noise are advantages. (source: sources/HRI2526.md)
  - Negative torque on the returning blade limits efficiency. (source: sources/HRI2526.md)
  - The review says adding more blades can improve torque but often lowers Cp; one three-bladed case reported much lower Cp and dynamic torque than the two-bladed rotor. (source: sources/vj12.md)
  - Endplates reduce leakage; the review notes a common recommendation that endplate diameter be about 10% larger than the turbine diameter. (source: sources/vj12.md)

- Self-starting and effective at low wind speeds. (source: sources/n1.md, sources/va1.md)
- Low efficiency due to high drag. (source: sources/n1.md)

- Typically consists of two semicircular blades creating differential drag. (source: sources/HRI2526.md)
- Tip speed ratio is between 0 and 1. (source: sources/HRI2526.md)
- Simple, low-cost construction and low noise. (source: sources/HRI2526.md)
- Suffers from negative torque on returning blade, reducing efficiency. (source: sources/HRI2526.md)
- Optimization includes blade count, overlap ratio, and augmentation devices. (source: sources/HRI2526.md)

![Source figure](vj12-fig12.jpg)
Original caption: Figure 12: Savonius rotor with endplates [19]. [[vj12|Source]]
![Source figure](vj12-fig19.jpg)
Original caption: Figure 19: Comparison of helical and conventional Savonius rotor [81]. [[vj12|Source]]

The review places Savonius operation around TSR 0.6-1.2 and peak Cp about 0.15-0.25, with self-starting as the main advantage. (source: sources/vj11.md)
It treats Savonius as the drag-based family used when low-speed startup matters more than peak efficiency. (source: sources/vj11.md)
In hybrid systems, Savonius is the startup element that helps cover Darrieus negative-torque regions at low TSR. (source: sources/vj11.md)
- The va8 patent defines Savonius-type VAWTs as primarily drag devices where downwind thrust exceeds upwind drag, and says its compartmented horizontal channel beams act similarly by trapping wind to generate drag torque. (source: sources/va8.md)
- The source identifies Savonius as a 1922 impulse rotor introduced by S. J. Savonius. (source: sources/va3.md)
- Modern variants evolved from half drums into fluted spiral-bladed designs that improve efficiency and reduce vibration. (source: sources/va3.md)
- The J-type rooftop design is a separate drag-based VAWT concept, but it shares the low-cost drag-rotor rationale. (source: sources/va5.md)
- The vj13 cluster study shows that a Savonius rotor can perform better when installed as part of a direction-aware cluster rather than as a standalone machine. (source: sources/vj13.md)
- The vj19 paper also shows that blade shape alone can shift rotational performance substantially even before guide vanes or hybridization are introduced. (source: sources/vj19.md)
- The `vj27` review adds a broad deflector-augmentation summary for Savonius rotors: simple flat plates can improve `Cp` by about `27%`, while one airfoil-shaped deflector case is reported to reach `50%` improvement. (source: sources/vj27.md)
- It also says two-bladed Savonius layouts remain the more attractive deflector partner than three-bladed layouts when performance, cost, and complexity are considered together. (source: sources/vj27.md)
- The same review treats correct deflector position and orientation as critical, and notes that the wrong orientation can make the turbine perform worse than the no-deflector baseline. (source: sources/vj27.md)

- The vj26 review adds that two-bucket Savonius systems generally outperform three-bucket cases in the studies it surveys, including one wind-tunnel review that also found two stages better than one or three. (source: sources/vj26.md)
- It also summarizes several passive improvement levers for drag rotors: blade vents, top and bottom caps, middle plates, curtain vanes, wing-wall shielding, and twisted blades. (source: sources/vj26.md)
- One cited stirring application in the review reports a twisted two-bladed drag rotor outperforming the three-bladed case, with an optimum twist angle near `30 degrees` for that use. (source: sources/vj26.md)

![Source figure](va3-fig10.jpg)
Original caption: Figure 10. Evolution of the Savonius design for water pumping from half drums into the fluted spiral bladed design. [[va3|Source]]

- Two-bladed configurations often achieve higher power coefficients. (source: sources/n2.md)
- Optimal aspect ratio typically around 1.5–2. (source: sources/n2.md)
- Overlap ratio ~0.15 performs well at low wind speeds (~<4 m/s). (source: sources/n2.md)
- Elliptical blades and ~45° twist can improve performance. (source: sources/n2.md)
- Endplates, curtains/shields, and auxiliary blades can reduce losses and improve efficiency. (source: sources/n2.md)
- In one hybrid-CFD study, a 38 mm shaft occupying about 66% of the Savonius overlap space was treated as a flow obstruction, and removing it increased average hybrid-rotor torque by 10.5% at 7 m/s. (source: sources/vj2.md)
- A 3D-CFD global optimization of circular-arc Savonius designs reports cP increases from `0.242` for its optimized two-blade design to `0.318` and `0.321` for optimized four- and six-blade designs at `AR = 1.5`; the paper finds little difference between its four- and six-blade results. (source: sources/va29.md)
- The same source's two-blade optimum uses practically zero overlap and TSR `1.2`, while its four- and six-blade optima resemble scooplet-based configurations. These are source-specific CFD findings, not a universal Savonius prescription. (source: sources/va29.md)
- The `va30` wind-tunnel campaign tested a two-bucket, `180-degree` semicircular geometry with bucket radius `0.25 m`; among its tested configurations, it reports strongest performance at inside-edge gap ratios `S/D = 0.10-0.15`. (source: sources/va30.md)
- It finds two buckets outperform three on peak power but have lower minimum static torque at some azimuths; its proposed response is two two-bucket stages offset by `90 degrees`. (source: sources/va30.md)

Related:
- [[VAWT]]
- [[HRI2526 Classical Savonius|Classical Savonius]]
- [[Helical Savonius]]
- [[Darrieus Turbine]]
- [[Hybrid VAWT]]
- [[vj2 Savonius-Darrieus Hybrid Wind Turbine]]
- [[vj2 Split Savonius Outside Darrieus Hybrid Wind Turbine]]
- [[Savonius Wind Turbine Cluster]]
- [[Wake Effect]]
- [[Wind Turbine Parameters]]
- [[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]]
- [[va3 Tip Speed Ratio Classification]]
- [[Wind Deflector]]
- [[vj27 Wind Deflector Shape]]
- [[vj27 Wind Deflector Position and Orientation]]

#concepts 
