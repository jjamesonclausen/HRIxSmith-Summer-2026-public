# Parameter Optimization Method of Contra-Rotating Vertical Axis Wind Turbine: Based on Numerical Simulation and Response Surface

Peng Zheng, Hexiang Zhang, Zutao Zhang, Waleed Salman, and Mansour Abdelrahman

## Abstract
The paper studies a contra-rotating vertical axis wind turbine (CRVAWT) for offshore wind energy recovery. The authors first verify a CFD model for an isolated VAWT against wind-tunnel data, then compare the proposed CRVAWT with the isolated VAWT. The CRVAWT has lower power coefficient but better stability. The study then investigates pitch angle, relative airfoil thickness, rotor spacing, and included angle between rotors, and uses a four-parameter three-level response-surface optimization to obtain an improved configuration. After optimization, the CRVAWT reaches a power coefficient of 0.1837, which is 36.68% higher than before optimization and 99.19% of the isolated VAWT value, while total torque is reduced by 96.96%.

## 1. Introduction
The paper frames offshore VAWTs as promising renewable-energy devices but notes that instability limits continued development. Contra-rotating VAWTs are presented as a way to improve wind-energy recovery and turbine stability.

The study uses STAR-CCM+ to simulate an isolated VAWT, compares the results with wind-tunnel tests, and then analyzes a CRVAWT. The authors combine CFD with response-surface optimization to improve turbine parameters.

Fig. 1. Research hotspots of wind turbines in recent years.

![Figure 1: Research hotspots of wind turbines in recent years.](../images/vj8-fig1.jpg)

## 2. Methodology
The study uses finite-volume CFD in STAR-CCM+ and checks model accuracy against wind-tunnel data. A research flow is presented that moves from isolated VAWT verification to CRVAWT analysis and then to parameter optimization.

Fig. 2. Schematic diagram of CRVAWT simulation analysis and optimization.

![Figure 2: Schematic diagram of CRVAWT simulation analysis and optimization.](../images/vj8-fig2.jpg)

### 2.1 Model Design
The CRVAWT consists of an upper rotor and a lower rotor with identical NACA0021 blades. The two rotors rotate in opposite directions and are connected by a disk generator and a floating platform.

The rotor radius is 1000 mm, rotor height is 1200 mm, blade chord is 265 mm, spacing between rotors is 0.25H, and pitch angle is 60 degrees based on prior experimental data.

Fig. 3. Model and parameters of CRVAWT.

![Figure 3: Model and parameters of CRVAWT.](../images/vj8-fig3.jpg)

### 2.2 Computational Domain and Mesh
The computational domain includes a fluid region and a rotating region. The isolated VAWT is used first to verify the model, then the CRVAWT is simulated using comparable mesh settings.

The paper uses a fine prismatic boundary layer mesh near the blades because the near-wall flow is intense and requires better resolution of pressure and velocity distributions.

Fig. 4. Calculation domain of VAWT.

![Figure 4: Calculation domain of VAWT.](../images/vj8-fig4.jpg)

Fig. 5. Topology diagram of the numerical mesh.

![Figure 5: Topology diagram of the numerical mesh.](../images/vj8-fig5.jpg)

Fig. 6. Torque of three turbulence models at different TSRs.

![Figure 6: Torque of three turbulence models at different TSRs.](../images/vj8-fig6.jpg)

## 3. Simulation Details
The CRVAWT model uses two coaxial rotors. The upper rotor rotates counterclockwise and the lower rotor rotates clockwise. The domain and mesh are similar to the isolated VAWT model, but the CRVAWT has more than 4 million cells and takes about 50 hours to simulate.

The isolated and contra-rotating turbines are compared under the same inflow velocity, and the CRVAWT shows lower single-rotor efficiency but much better overall stability because the upper and lower rotor torques largely cancel.

Fig. 7. Computational domain of CRVAWT.

![Figure 7: Computational domain of CRVAWT.](../images/vj8-fig7.jpg)

Fig. 8. Torque comparison between VAWT and CRVAWT.

![Figure 8: Torque comparison between VAWT and CRVAWT.](../images/vj8-fig8.jpg)

### 3.1 Parameter Selection
The study varies four parameters: blade pitch angle, relative airfoil thickness, rotor spacing, and included angle between rotors.

Fig. 9. Schematic diagram of the blade pitch angle.

![Figure 9: Schematic diagram of the blade pitch angle.](../images/vj8-fig9.jpg)

Fig. 10. Cross sections of four airfoils.

![Figure 10: Cross sections of four airfoils.](../images/vj8-fig10.jpg)

Fig. 11. Schematic diagram of spacing and included angle between rotors.

![Figure 11: Schematic diagram of spacing and included angle between rotors.](../images/vj8-fig11.jpg)

## 4. Results and Discussion
The pitch-angle study shows that the average power coefficient is highest at 0 degrees. The pressure difference on the blade surfaces explains the torque changes.

For airfoil selection, the paper compares NACA0015, NACA0018, NACA0021, and NACA0024. NACA0018 and NACA0021 give similar power coefficients, and the paper suggests the optimum lies between them.

Rotor spacing also matters: larger spacing reduces rotor interaction and improves power coefficient, moving the CRVAWT closer to isolated VAWT performance.

The included-angle study shows how torque and wake structure change as the upper and lower rotors are phased differently.

Fig. 12. Simulation results and analysis of blade pitch angle.

![Figure 12: Simulation results and analysis of blade pitch angle.](../images/vj8-fig12.jpg)

Fig. 13. Diagrams of Cp of the upper and lower rotors under different airfoils.

![Figure 13: Diagrams of Cp of the upper and lower rotors under different airfoils.](../images/vj8-fig13.jpg)

Fig. 14. Upper rotor surface pressures of four types of airfoils.

![Figure 14: Upper rotor surface pressures of four types of airfoils.](../images/vj8-fig14.jpg)

Fig. 15. Simulation results and analysis of rotor spacing.

![Figure 15: Simulation results and analysis of rotor spacing.](../images/vj8-fig15.jpg)

Fig. 16. The variation of torque and time of CRVAWT under different included angles.

![Figure 16: The variation of torque and time of CRVAWT under different included angles.](../images/vj8-fig16.jpg)

Fig. 17. Response surface fitting results.

![Figure 17: Response surface fitting results.](../images/vj8-fig17.jpg)

Fig. 18. Flow chart of CRVAWT parameter optimization method.

![Figure 18: Flow chart of CRVAWT parameter optimization method.](../images/vj8-fig18.jpg)

Fig. 19. Application of the optimized CRVAWT for offshore wind energy recovery.

![Figure 19: Application of the optimized CRVAWT for offshore wind energy recovery.](../images/vj8-fig19.jpg)

Fig. 20. The design, optimization, and scheme of CRVAWT.

![Figure 20: The design, optimization, and scheme of CRVAWT.](../images/vj8-fig20.jpg)

## 5. Conclusions
The CRVAWT is more stable than the isolated VAWT but initially has lower power coefficient. After response-surface optimization, the power coefficient rises to 0.1837 and the total torque is drastically reduced. The paper concludes that the optimized CRVAWT is well suited to offshore floating platforms.

## References
[1] Li et al. (2016), experimental data used to verify the isolated VAWT model.

[2] O'Meara and Mueller (1987), cited for the link between pressure difference and rotor torque.

[3] Poguluri et al. (2021), cited for tip loss effects.

[4] Lee et al. (2022), cited for tip loss effects.
