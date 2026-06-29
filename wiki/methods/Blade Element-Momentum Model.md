## Blade Element-Momentum Model

Load-prediction method used to estimate VAWT performance from blade aerodynamics and momentum theory. (source: sources/vj4.md)

![Figure 2: Predicted and experimental power coefficients for the SANDIA wind turbine](../../images/vj4-fig2.jpg)
![Figure 3: Predicted and experimental tangential force coefficients during a rotor revolution](../../images/vj4-fig3.jpg)

- The paper uses a Double Disk - Multiple Streamtube implementation of BE-M. (source: sources/vj4.md)
- It adds dynamic stall handling with the Boeing-Vetrol model and high-angle-of-attack extension with Viterna-Corrigan. (source: sources/vj4.md)
- It is used here to compare rotor architectures while holding solidity and swept area fixed. (source: sources/vj4.md)
- The method was validated against Sandia power-coefficient data and tangential force measurements. (source: sources/vj4.md)

Related:
- [[Darrieus Turbine]]
- [[H-VAWT]]
- [[Wind Turbine Parameters]]

#methods