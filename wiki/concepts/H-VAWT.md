---
Created:
Updated: 2026-07-02
Sources:
- [[sources/va2.md]]
- [[sources/vj4.md]]
Source_count: 2
Tags:
- concepts
---
## H-Type Vertical-Axis Wind Turbine (H-VAWT)

Vertical-axis wind turbine with straight blades arranged around the rotor, often used as a benchmark for aerodynamic modeling and optimization. (source: sources/va2.md)

![Figure 1: Schematic of VAWT blade forces at different azimuthal angles](../../images/va2-fig1.jpg)

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

![Fig. 20. Novel approach to the DMS model in an H-Rotor VAWT influenced by a wind in skewed flow.](../../images/va9-fig20.jpg)

Related: [[VAWT]], [[Darrieus Turbine]], [[HAWT vs VAWT]], [[Kriging Surrogate Model]], [[CST Parameterization]], [[Multi-Island Genetic Algorithm]], [[Straight-bladed Darrieus]], [[Double-Multiple Streamtube Model]]
 
#concepts 
