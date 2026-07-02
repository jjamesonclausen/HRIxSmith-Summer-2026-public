---
Created:
Updated: 2026-07-02
Sources:
- [[va9]]
- [[vj10]]
- [[vj4]]
Source_count: 3
Tags:
- methods
---
## Blade Element-Momentum Model

Load-prediction method used to estimate wind-turbine performance from blade aerodynamics and momentum theory. (source: sources/vj4.md, sources/vj10.md)

![Figure 2: Predicted and experimental power coefficients for the SANDIA wind turbine](../../images/vj4-fig2.jpg)
![Figure 3: Predicted and experimental tangential force coefficients during a rotor revolution](../../images/vj4-fig3.jpg)

- The paper uses a Double Disk - Multiple Streamtube implementation of BE-M. (source: sources/vj4.md)
- It adds dynamic stall handling with the Boeing-Vetrol model and high-angle-of-attack extension with Viterna-Corrigan. (source: sources/vj4.md)
- It is used here to compare rotor architectures while holding solidity and swept area fixed. (source: sources/vj4.md)
- The method was validated against Sandia power-coefficient data and tangential force measurements. (source: sources/vj4.md)
- In the wind-shear HAWT paper, BEM is used to design chord and twist distributions for a 100 kW turbine and to calculate lift, thrust, and power coefficients along the blade length. (source: sources/vj10.md)
- The same paper combines BEM with a power-law wind-shear model by dividing the swept area into vertical slices, so each sector receives the wind speed corresponding to its height. (source: sources/vj10.md)
- The authors describe this as a way to improve classical BEM for wind-shear effects while keeping calculation cost close to the classical method. (source: sources/vj10.md)
- The va9 paper classifies BEM variants for Darrieus VAWTs into single streamtube, multiple streamtube, and double-multiple streamtube models. (source: sources/va9.md)
- It describes BEM as combining blade element theory with momentum theory to study airflow behavior and forces on the blades. (source: sources/va9.md)
- It also proposes a sliced DMS extension where complex blade forms are divided into flow-parallel slices, each treated as a virtual Darrieus VAWT before integrating slice performance. (source: sources/va9.md)

![Figure 4: sectors on rotor swept area](../../images/vj10-fig4.jpg)
![Fig. 16. Double-multiple streamtube model diagram.](../../images/va9-fig16.jpg)

Related:
- [[Darrieus Turbine]]
- [[H-VAWT]]
- [[Wind Turbine Parameters]]
- [[Wind Shear]]
- [[Double-Multiple Streamtube Model]]

#methods
