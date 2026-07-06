---
Created:
Updated: 2026-07-06
Sources:
- [[va2]]
- [[va16]]
- [[va15]]
- [[va14]]
- [[va9]]
- [[va11]]
- [[vj14]]
- [[vj4]]
Source_count: 8
Tags:
- concepts
---
## H-Type Vertical-Axis Wind Turbine (H-VAWT)

Vertical-axis wind turbine with straight blades arranged around the rotor, often used as a benchmark for aerodynamic modeling and optimization. (source: sources/va2.md)

![Source figure](../../images/va2-fig1.jpg)
Original caption: Figure 1: Schematic of VAWT blade forces at different azimuthal angles [[va2|Source]]

- Geometry:
  - Straight blades are arranged around the rotor in an H-type layout. (source: sources/va2.md)
  - The straight-bladed form keeps blade radius constant over its length. (source: sources/vj4.md)
- Performance:
  - The paper validates the H-VAWT model against wind-tunnel data and evaluates it across tip-speed ratios. (source: sources/va2.md)
  - The H-VAWT is used as a benchmark for optimization. (source: sources/va2.md)
- Tradeoffs:
  - The straight-bladed H-rotor is easier to model and optimize than some curved variants. (source: sources/vj4.md)
  - It still shows strong azimuth-dependent loading and cyclic variation. (source: sources/va2.md)

- The paper validates an H-VAWT CFD model against the Musgrove wind-tunnel experiment. (source: sources/va2.md)
- The study uses a NACA0015 baseline airfoil and evaluates performance across tip-speed ratios. (source: sources/va2.md)
- H-VAWT flow loading varies strongly with azimuth angle, with lift and drag contributing differently across a full rotation. (source: sources/va2.md)
- The paper also treats H-VAWT as a VAWT subtype suited to optimization with surrogate models. (source: sources/va2.md)
- In the small-VAWT architecture study, the straight-bladed H-Darrieus case had larger pulsating loads than the helical case. (source: sources/vj4.md)
- The helical configuration widened the range near maximum CP and reduced fatigue-driving oscillations. (source: sources/vj4.md)
- The va9 paper uses an H-rotor in skewed flow as an example for its sliced DMS approach, where the blade follows an elliptical path in some slices and the effective blade profile changes with blade angle. (source: sources/va9.md)
- The va11 wake review treats the H-rotor as the main modern straight-bladed VAWT for urban use and dense layouts because its wake can recover quickly and support closer turbine spacing in some configurations. (source: sources/va11.md)
- It also frames H-rotor wake asymmetry, counter-rotating vortices, and strong dynamic-stall effects as central aerodynamic features of the subtype. (source: sources/va11.md)
- The va14 study adds a large CFD characterization of 2-, 3-, and 4-bladed Darrieus H-type turbines, using solidity from 0.09 to 0.36 and showing that optimal tip-speed ratio shifts strongly with solidity. (source: sources/va14.md)
- It also reports that near the optimal operating range, peak `Cp` is almost independent of blade number at fixed `Rec`. (source: sources/va14.md)
- The va15 experiment adds direct self-start evidence for a 3-bladed H-Darrieus: high solidity, a thick symmetric profile, small negative pitch, and larger aspect ratio all helped startup in the tested cases. (source: sources/va15.md)
- The va16 panel-method study adds a spanwise-performance view for straight-bladed H-rotors, showing that larger `H/D` can improve peak `Cp` at fixed solidity while lower `H/D` strengthens tip-vortex influence near the blade tip. (source: sources/va16.md)
- The vj14 case study adds a real deployed H-Darrieus turbine with a `3.5 m` diameter, `3 m` blade height, `5 kW` nominal capacity, and a `15.6 m` mast on the Bialystok campus. (source: sources/vj14.md)
- It reports that the prototype's poor performance was dominated by the local wind resource rather than by the LCA method itself. (source: sources/vj14.md)

![Source figure](../../images/va9-fig20.jpg)
Original caption: Fig. 20. Novel approach to the DMS model in an H-Rotor VAWT influenced by a wind in skewed flow. [[va9|Source]]

Related: [[VAWT]], [[Darrieus Turbine]], [[HAWT vs VAWT]], [[Kriging Surrogate Model]], [[CST Parameterization]], [[Multi-Island Genetic Algorithm]], [[Straight-bladed Darrieus]], [[Double-Multiple Streamtube Model]], [[H-rotor Wake Aerodynamics]]
 
#concepts 
