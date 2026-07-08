---
Created: 2026-06-26
Updated: 2026-07-07
Sources: [[va2]], [[vj4]], [[va9]], [[va11]], [[va14]], [[va15]], [[vj15]], [[va16]], [[vj14]], [[va25]], [[va26]], [[va27]], [[vj25]]
Source_count: 13
Tags: #concepts
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
The vj15 study adds that harmonic variable pitch can improve both startup and power for an H-type rotor, with Case 1 at a 3-degree amplitude reported as best. (source: sources/vj15.md)
- The va16 panel-method study adds a spanwise-performance view for straight-bladed H-rotors, showing that larger `H/D` can improve peak `Cp` at fixed solidity while lower `H/D` strengthens tip-vortex influence near the blade tip. (source: sources/va16.md)
- The vj14 case study adds a real deployed H-Darrieus turbine with a `3.5 m` diameter, `3 m` blade height, `5 kW` nominal capacity, and a `15.6 m` mast on the Bialystok campus. (source: sources/vj14.md)
- It reports that the prototype's poor performance was dominated by the local wind resource rather than by the LCA method itself. (source: sources/vj14.md)
- The va25 paper adds a 3-bladed straight-bladed H-rotor CFD reference model and uses it to compare how airfoil family and camber orientation affect startup and `Cp` over low-to-mid TSR operation. (source: sources/va25.md)
- That source reports cambered-in `NACA6712` as best for low TSR, symmetric `E474` as best for mid-to-high TSR, and flipped `Clark Y` as the best cambered-out case for startup-oriented improvement. (source: sources/va25.md)
- The va26 paper adds a fixed-pitch-angle study on a low-solidity 3-bladed H-rotor and reports an optimum of `-2` degrees at `TSR = 4`. (source: sources/va26.md)
- It also argues that the way pitch redistributes instantaneous moment over azimuth makes dynamic pitching a promising next step for H-rotor performance improvement. (source: sources/va26.md)
- The va27 paper adds a one-bladed low-solidity H-type reference rotor used to isolate how symmetric airfoil-shape parameters affect power performance in deep dynamic stall. (source: sources/va27.md)
- The vj25 paper adds a sizing-rule view for straight-bladed H-rotors, arguing that lower rotor aspect ratio (`h/R`) increases blade Reynolds number and can slightly improve `Cp` while lowering rotational speed in its `1 kW` `NACA 0018` case study. (source: sources/vj25.md)
- That source compares converged `AR = 2` and `AR = 0.4` designs and reports `cpmax` changing from `0.464` to `0.475` while rotor speed drops from `299 rpm` to `137 rpm`. (source: sources/vj25.md)

![Source figure](../../images/va9-fig20.jpg)
Original caption: Fig. 20. Novel approach to the DMS model in an H-Rotor VAWT influenced by a wind in skewed flow. [[va9|Source]]

Related: [[VAWT]], [[Darrieus Turbine]], [[HAWT vs VAWT]], [[Kriging Surrogate Model]], [[CST Parameterization]], [[Multi-Island Genetic Algorithm]], [[Straight-bladed Darrieus]], [[Double-Multiple Streamtube Model]], [[Multiple Stream Tube Model]], [[H-rotor Wake Aerodynamics]], [[va25 Reference H-Rotor Darrieus VAWT]], [[va25 Blade Airfoil Profile]], [[va25 Cambered Airfoil Orientation]], [[va26 3-Bladed H-Type VAWT]], [[va26 Fixed Blade Pitch Angle]], [[va27 Reference One-Bladed H-Type VAWT]], [[va27 Airfoil Relative Maximum Thickness]], [[va27 Airfoil Maximum-Thickness Position]], [[va27 Leading-Edge Radius Index]], [[vj25 Rotor Aspect Ratio]], [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]], [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]]
 
#concepts 
