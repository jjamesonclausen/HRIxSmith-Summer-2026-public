#sources
# Simulating Dynamic Stall in a 2D VAWT: Modeling strategy, verification and validation with Particle Image Velocimetry data

C. J. Simão Ferreira, H. Bijl, G. van Bussel, G. van Kuik

## Abstract

The implementation of wind energy conversion systems in the built environment renewed interest in vertical axis wind turbines (VAWTs), which offer advantages over horizontal axis wind turbines (HAWTs) in built environments. VAWTs exhibit unsteady aerodynamics because angle of attack, perceived velocity, and Reynolds number vary with azimuth. Dynamic stall is therefore an intrinsic effect at low tip speed ratios and has a significant impact on loads and power.

This paper uses computational fluid dynamics (CFD) to model a 2D single-bladed VAWT section and compares turbulence models, grid refinement, and validation strategies against Particle Image Velocimetry (PIV) data. The authors compare URANS models (Spalart-Allmaras and k-epsilon) with LES and DES, examine sensitivity to space and time refinement, and evaluate PIV as a validation source. The results show that DES agrees best with the experimental vorticity evolution, that the model is sensitive to grid refinement, and that PIV-based vorticity comparison is more useful than blade-force comparison for this problem.

## 1. Introduction

The increasing awareness of environmentally sustainable housing and cities has driven promotion of wind energy conversion systems for the built environment. VAWTs reappear in this context because they offer low sound emission, better aesthetics, insensitivity to yaw wind direction, and increased power output in skewed flow.

Dynamic stall is an inherent effect of VAWT operation at low tip speed ratios. It strongly affects both load and power. Modeling this behavior presents several challenges: time accuracy, moving geometry, large vorticity shedding, blade-vortex interaction, and changing lift/drag dominance over the rotor cycle.

This numerical model simulates the experimental work by Simão Ferreira et al. for Re = 50,000 and tip speed ratio λ = 2.

## 2. Model Geometry and Computational Grid

The model is a 2D representation of the experimental setup. The CFD grid includes four non-conformal sub-grids. The rotor is a 0.4 m diameter single-bladed Darrieus VAWT represented by a 0.05 m chord NACA0015 airfoil and a 0.05 m rotor axis.

The inlet and outlet are placed 10D upwind and 14D downwind of the rotor. Moving sub-grids are used for the rotor and blade regions, while the wind tunnel region remains fixed. The fine grid includes 3305 nodes over the airfoil surface and a total model size of approximately 1.6 million cells.

Figure 1. Diagram of the model geometry, sub-grid distribution and boundary conditions.

![Figure 1: Diagram of the model geometry, sub-grid distribution and boundary conditions](../images/vj5-fig1.jpg)

## 3. Simulated Flow Conditions

The simulation represents flow at λ = 2 and incoming flow U∞ = 7.5 m/s. The reduced frequency is k = 0.125, placing the problem in the unsteady aerodynamics region. Several rotor revolutions are required before a periodic post-transient solution is found.

## 4. Validation of the Results of Different Turbulence Models

Four turbulence models are compared: Spalart-Allmaras, k-epsilon, LES, and DES. Validation is based on comparing vorticity evolution near the airfoil at θ = 90° and θ = 120° to PIV measurements.

Figure 2. PIV experimental data of the evolution of the circulation of leading edge separated vortex for λ = 2 at 90°, 108°, 133° and 158°.

![Figure 2: PIV experimental data of the evolution of the circulation of leading edge separated vortex for λ = 2 at 90°, 108°, 133° and 158°](../images/vj5-fig2.jpg)

Figure 3. PIV experimental data of the evolution of the counter-clockwise vorticity shed after the roll-up of the trailing edge vorticity.

![Figure 3: PIV experimental data of the evolution of the counter-clockwise vorticity shed after the roll-up of the trailing edge vorticity](../images/vj5-fig3.jpg)

### 4.1 URANS Models

Spalart-Allmaras and k-epsilon underpredict leading-edge vorticity shedding and fail to capture the trailing-edge wake roll-up seen in the experiments. Time grid refinement does not materially improve this behavior. A maximum time step of Δt = 1/4°/ω is recommended.

Figure 4. Vorticity field at θ = 90°, Spalart-Allmaras model.

![Figure 4: Vorticity field at θ = 90°, Spalart-Allmaras model](../images/vj5-fig4.jpg)

Figure 5. Vorticity field at θ = 120°, Spalart-Allmaras model.

![Figure 5: Vorticity field at θ = 120°, Spalart-Allmaras model](../images/vj5-fig5.jpg)

Figure 6. Vorticity field at θ = 90°, k-ε model.

![Figure 6: Vorticity field at θ = 90°, k-ε model](../images/vj5-fig6.jpg)

Figure 7. Vorticity field at θ = 120°, k-ε model.

![Figure 7: Vorticity field at θ = 120°, k-ε model](../images/vj5-fig7.jpg)

### 4.2 LES

LES improves on the URANS models by capturing larger-scale shedding and wake roll-up, but still triggers the trailing-edge wake too early relative to experiment.

Figure 8. Vorticity field at θ = 90°, Large Eddy Simulation.

![Figure 8: Vorticity field at θ = 90°, Large Eddy Simulation](../images/vj5-fig8.jpg)

Figure 9. Vorticity field at θ = 120°, Large Eddy Simulation.

![Figure 9: Vorticity field at θ = 120°, Large Eddy Simulation](../images/vj5-fig9.jpg)

### 4.3 DES

DES gives the closest agreement with experiment among the tested models. The paper attributes this to improved wall-region modeling while retaining LES-like treatment outside the boundary layer.

Figure 10. Vorticity field at θ = 90°, Detached Eddy Simulation.

![Figure 10: Vorticity field at θ = 90°, Detached Eddy Simulation](../images/vj5-fig10.jpg)

Figure 11. Vorticity field at θ = 120°, Detached Eddy Simulation.

![Figure 11: Vorticity field at θ = 120°, Detached Eddy Simulation](../images/vj5-fig11.jpg)

## 5. Comparison of Force Simulation

Tangential and normal force histories are compared across the models. The main differences are non-zero normal force at θ = 0 in URANS, different azimuthal locations for force maxima, and higher-frequency oscillations in LES/DES.

Figure 12. Tangential and normal force in the blade, SA model, Δt = 1/2°/ω. Instantaneous values over three rotations.

![Figure 12: Tangential and normal force in the blade, SA model, Δt = 1/2°/ω](../images/vj5-fig12.jpg)

Figure 13. Tangential and normal force in the blade, k-ε model, Δt = 1/2°/ω. Instantaneous values over three rotations.

![Figure 13: Tangential and normal force in the blade, k-ε model, Δt = 1/2°/ω](../images/vj5-fig13.jpg)

Figure 14. Tangential and normal force in the blade, DES, Δt = 1/4°/ω. Instantaneous values over five rotations.

![Figure 14: Tangential and normal force in the blade, DES, Δt = 1/4°/ω](../images/vj5-fig14.jpg)

Figure 15. Tangential and normal force in the blade, LES model, Δt = 1/4°/ω. Instantaneous values over four rotations.

![Figure 15: Tangential and normal force in the blade, LES model, Δt = 1/4°/ω](../images/vj5-fig15.jpg)

## 6. Verification to Grid Sensitivity

The DES model is tested for time and space grid sensitivity. The results show some sensitivity, but less than the laminar model discussed in the cited prior work.

### 6.1 Time Grid Refinement

Further time refinement produces only limited changes once the first refinement has been made.

Figure 16. Vorticity field at θ = 90°, Δt = 1/8°/ω.

![Figure 16: Vorticity field at θ = 90°, Δt = 1/8°/ω](../images/vj5-fig16.jpg)

Figure 17. Vorticity field at θ = 90°, Δt = 1/16°/ω.

![Figure 17: Vorticity field at θ = 90°, Δt = 1/16°/ω](../images/vj5-fig17.jpg)

Figure 18. Effect on tangential and normal force of change of the time grid refinement.

![Figure 18: Effect on tangential and normal force of change of the time grid refinement](../images/vj5-fig18.jpg)

### 6.2 Space Grid Refinement

Coarsening the blade sub-grid over-generates vorticity, but the force impact is smaller than in the laminar model.

Figure 19. Vorticity field at θ = 90°, Δt = 0.25°/ω, 2 times coarser grid.

![Figure 19: Vorticity field at θ = 90°, Δt = 0.25°/ω, 2 times coarser grid](../images/vj5-fig19.jpg)

Figure 20. Vorticity field at θ = 90°, Δt = 0.25°/ω.

![Figure 20: Vorticity field at θ = 90°, Δt = 0.25°/ω](../images/vj5-fig20.jpg)

Figure 21. Effect on tangential and normal force of change of the space grid refinement.

![Figure 21: Effect on tangential and normal force of change of the space grid refinement](../images/vj5-fig21.jpg)

## 7. Verification Convergence Error

The authors test whether the high-frequency force oscillations stem from convergence error by comparing several runs with different iteration counts and time steps. The comparison does not allow a final conclusion.

Figure 22. The effect of convergence on tangential and normal force of change of the convergence iteration.

![Figure 22: The effect of convergence on tangential and normal force of change of the convergence iteration](../images/vj5-fig22.jpg)

## 8. Conclusions

DES best matches the experimental dynamic-stall behavior. URANS models are insufficient for the large eddies, while LES performs worse than DES because of wall-region modeling limitations.

The paper concludes that PIV velocity and vorticity data are more useful for validating this type of CFD than comparing forces alone. Future work should focus on better grid control, turbulence sub-models, wall treatment, airfoil-shape effects, and friction-drag modeling.

## 9. Acknowledgments

The authors thank Dr. van Zuijlen (DUWIND) for help and remarks.

## 10. Bibliography

[1] C. J. Simão Ferreira, G. van Bussel, and G. van Kuik. 2D PIV visualization of dynamic stall on a vertical axis wind turbine. 45th AIAA Aerospace Sciences Meeting and Exhibit / ASME Wind Energy Symposium, 2007.

[2] S. Mertens, G. van Kuik, and G. van Bussel. Performance of a H-Darrieus in the skewed flow on a roof. Journal of Solar Energy Engineering, 125:433-440, 2003.

[3] C. J. Simão Ferreira, G. van Bussel, and G. van Kuik. Wind tunnel hotwire measurements, flow visualization and thrust measurement of a VAWT in skew. 44th AIAA Aerospace Sciences Meeting and Exhibit / ASME Wind Energy Symposium, 2006.

[4] C. J. Simão Ferreira, G. van Bussel, and G. van Kuik. 2D CFD simulation of dynamic stall on a Vertical Axis Wind Turbine: verification and validation with PIV measurements. 45th AIAA Aerospace Sciences Meeting and Exhibit / ASME Wind Energy Symposium, 2007.

[5] M. O. L. Hansen and D. N. Søresen. CFD model for Vertical Axis Wind Turbine. Wind Energy for the New Millennium, 2001.

[6] A. Allet, S. Hallé, and I. Paraschivoiu. Numerical simulation of dynamic stall around an airfoil in Darrieus motion. Journal of Solar Energy Engineering, 1999.

[7] I. Paraschivoiu and A. Allet. Aerodynamic analysis of the Darrieus wind turbines including dynamic-stall effects. Journal of Propulsion and Power, 1988.

[8] I. Paraschivoiu and C. Béguiér. Visualization, measurements and calculations of dynamic stall for a similar motion of VAWT. European Wind Energy Conference, 1998.

[9] I. Paraschivoiu. Wind Turbine Design - With Emphasis on Darrieus Concept. 2002.

[10] Jonas Bredberg. On two equation eddy-viscosity models. Technical Report 01/8, 2001.

[11] Fluent User's Manual. Fluent Inc.

[12] P. R. Spalart and S. Almaras. A one-equation turbulence model for aerodynamic flows. AIAA-92-0439, 1992.

[13] P. R. Spalart. Strategies for turbulence modelling and simulations. International Journal of Heat and Fluid Flow, 2000.

[14] S. Dahlström and L. Davidson. Large eddy simulation of the flow around an airfoil. 39th AIAA Aerospace Sciences Meeting and Exhibit, 2001.

[15] P. R. Spalart. Topics in detached-eddy simulation. Computational Fluid Dynamics 2004, 2006.
