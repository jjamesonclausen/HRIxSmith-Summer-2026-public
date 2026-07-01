#sources
# Simulating Dynamic Stall in a 2D VAWT: Modeling strategy, verification and validation with Particle Image Velocimetry data

C. J. Simão Ferreira, H. Bijl, G. van Bussel, G. van Kuik

## Abstract

The implementation of wind energy conversion systems in the built environment renewed the interest and the research on Vertical Axis Wind Turbines (VAWT), which in this application present several advantages over Horizontal Axis Wind Turbines (HAWT). The VAWT has an inherent unsteady aerodynamic behavior due to the variation of angle of attack with the angle of rotation, perceived velocity and consequentially Reynolds number. The phenomenon of dynamic stall is then an intrinsic effect of the operation of a Vertical Axis Wind Turbine at low tip speed ratios, having a significant impact in both loads and power.

The complexity of the unsteady aerodynamics of the VAWT makes it extremely attractive to be analyzed using Computational Fluid Dynamics (CFD) models, where an approximation of the continuity and momentum equations of the Navier-Stokes equations set is solved. The complexity of the problem and the need for new design approaches for VAWT for the built environment has driven the authors of this work to focus the research of CFD modeling of VAWT on:
comparing the results between commonly used turbulence models:
URANS (Spalart-
Allmaras and k-) and large eddy models (Large Eddy Simulation and Detached Eddy
Simulation)
verifying the sensitivity of the model to its grid refinement (space and time),
evaluating the suitability of using Particle Image Velocimetry (PIV) experimental data for
model validation.
The 2D model created represents the middle section of a single bladed VAWT with infinite
aspect ratio.
The model simulates the experimental work of flow field measurement using
Particle Image Velocimetry by Simao Ferreira et al [1] for a single bladed VAWT.
The results show the suitability of the PIV data for the validation of the model, the need
for accurate simulation of the large eddies and the sensitivity of the model to grid refinement.

## 1. Introduction

The increasing awareness of the need for environmentally sustainable housing and cities has
driven the promotion of wind energy conversion systems for the built environment. One of
the results of the development of solutions for the built environment is the reappearance of
Vertical Axis Wind Turbines (VAWTs). In the built environment, the VAWT presents several
advantages over the more common Horizontal Axis Wind Turbines (HAWTs), namely: its low
sound emission (consequence of its operation at lower tip speed ratios), better esthetics due to
its three-dimensionality, its insensitivity to yaw wind direction and its increased power output
in skewed flow (see Mertens et al [2] and Simao Ferreira et al [3]).

The phenomenon of dynamic stall is an inherent effect of the operation of a VAWT at low tip
speed ratios (). The presence of dynamic stall has significant impact on both load and power.
Modeling the VAWT in dynamic stall presents five immediate challenges:
 The unsteady component of the flow requires a time accurate model, adding an extra
dimension (time) to the numerical grid.
 The geometry of the rotor does not allow for important spatial/time grid simplifications to
 be applied (example: moving reference frames or radial symmetry).
 The large amount of shed vorticity implies that the model could be sensitive to numerical
dissipation.
 The geometry of a Vertical Axis Wind Turbine results in blade-vortex interaction at the
downwind passage of the blade between the blade and the shed vorticity that was generated
at the upwind passage. This means that the development of the shed vorticity must be
correctly modeled inside the entire rotor diameter; in order to avoid numerical dissipation,
the spatial resolution of the grid must be very fine not only in the immediate vicinity of the
blades but over the entire rotor.
 The variation of angle of attack of the blade with azimuth angle implies a varying
relation/dominance between lift and drag force on the blade (resulting in instants during the
rotation where the VAWT is actually being decelerated because

## 2. Model Geometry and Computational Grid

The geometry of the model is a 2D representation of the experimental setup of Simao Ferreira et
al [1]. The CFD grid presents a slight discrepancy later discovered between the location of the
The model's wall boundary conditions consists of two walls spaced 1.25m apart, where a 0.4m diameter single-
bladed Darrieus VAWT is placed.

The rotor is represented by an 0.05m chord NACA0015 airfoil and the 0.05m rotor axis. The
rotor axis is placed over the symmetry position of the wind tunnel. The inlet and outlet boundary
conditions are placed respectively 10D upwind and 14D downwind of the rotor, allowing a full
development of the wake.

The model comprises a 2D spatial grid, simulating the conditions at the middle cross-section of
the experimental setup. The grid is composed of four non-conformal sub-grids, each a structured
grid of quadrilateral elements. Figure 1 presents a diagram of the shape and location of each
sub-grid and the wall boundary conditions representing the airfoil/blade, wind tunnel walls and
rotor axis (the flow inlet and outlet boundary conditions are not represented).

The use of moving sub-grids is necessary due to the movement of the rotor elements. Thus, the
sub-grids Rotor Diameter, Blade sub-grid I, and Blade sub-grid II rotate with an angular velocity
= 75rad/s, while the sub-grid Wind Tunnel remains fixed. The option of dividing the rotor
space in three non-conformal sub-grids allows the use of a structured grid without compromising
its quality or requiring a large mesh with over refinement in areas of lower importance.

Figure 1. Diagram of the model geometry, sub-grid distribution and boundary conditions.

![Figure 1: Diagram of the model geometry, sub-grid distribution and boundary conditions](../images/vj5-fig1.jpg)

## 3. Simulated Flow Conditions

The simulation aimed at representing the flow conditions of the experimental work for λ = 2 and
incoming flow U = 7.5m/s. The level of unsteadiness is determined by the reduced frequency
k, defined as k = ω.c/2V, where ω is the angular frequency of the unsteadiness, c is the blade’s
chord and V is the velocity of the blade. In this experiment, due to the variation of V with
rotation angle, k was defined as k = ω.c/(2.λ.V∞) = ω.c/(2.ω.R) = c/(2.R), where λ is the tip
speed ratio and R is the radius of rotation. For this experimental work k = 0.125, placing the
work in the unsteady aerodynamics region.

Due to the importance of the induction of the rotor, it is necessary to perform a simulation
for several rotations until a fully developed wake is present. All values presented in this paper
relate to the revolutions of the rotor after a periodic post-transient solution is found.

## 4. Validation of the Results of Different Turbulence Models

Four different turbulence models where used in this work, complementing the analysis with
a Laminar model by Simao Ferreira et al [4]; two URANS (Spallart-Almaras and k-) and two
large eddy models (DES and LES).

The simulations results are validated against the experimental results of Simao Ferreira et
al [1] for the case of λ = 2. These results, of which Figures 2 and 3 are an example, show that
the flow is characterized by the shedding to the flow of strong vortices; this shedding of vorticity
is located:
 at the leading edge, resulting of a leading edge separation where the clockwise vortices
detach from the surface
 at the trailing edge, where a wake is formed from the pressure side boundary layer and
the boundary layer developed in the suction side after the point of leading edge separation-
reattachment; this wake experiences a roll up due to the strong vorticity.

Figure 2. PIV experimental data of the evolution of the circulation of leading edge separated vortex for λ = 2 at 90°, 108°, 133° and 158°.

![Figure 2: PIV experimental data of the evolution of the circulation of leading edge separated vortex for λ = 2 at 90°, 108°, 133° and 158°](../images/vj5-fig2.jpg)

Figure 3. PIV experimental data of the evolution of the counter-clockwise vorticity shed after the roll-up of the trailing edge vorticity.

![Figure 3: PIV experimental data of the evolution of the counter-clockwise vorticity shed after the roll-up of the trailing edge vorticity](../images/vj5-fig3.jpg)

### 4.1 URANS Models

Unsteady Reynolds-Averaged Navier-Stokes aims at reducing the computational effort by solving
the Reynolds averaged form of the Navier-Stokes equations (see Bredberg [10]), however requiring
the modeling of the Reynolds stresses originated from the averaging method. In the range
of possible models are eddy-viscosity models which assume that the Reynolds stresses can be
estimated by a relation of the eddy viscosity and the velocity spatial derivatives. In this work
two of the most popular URANS eddy viscosity models are used: the one-equation Spallart-
Almaras (S-A) and the two-equations k- model. The S-A used is the implementation in the
CFD package Fluent (see reference [11]) of the model proposed by Sparllat and Almaras [12].
The k- model is the standard implementation in Fluent [11] referred as Standard k-.

Figure 4. Vorticity field at θ = 90°, Spalart-Allmaras model.

![Figure 4: Vorticity field at θ = 90°, Spalart-Allmaras model](../images/vj5-fig4.jpg)

Figure 5. Vorticity field at θ = 120°, Spalart-Allmaras model.

![Figure 5: Vorticity field at θ = 120°, Spalart-Allmaras model](../images/vj5-fig5.jpg)

Figure 6. Vorticity field at θ = 90°, k-ε model.

![Figure 6: Vorticity field at θ = 90°, k-ε model](../images/vj5-fig6.jpg)

Figure 7. Vorticity field at θ = 120°, k-ε model.

![Figure 7: Vorticity field at θ = 120°, k-ε model](../images/vj5-fig7.jpg)

### 4.2 LES

Previous attempts on the simulation of 2D VAWT flow (see Hansen et al [5] , Allet et al [6]
, Paraschivoiu et al [7] , Paraschivoiu et al [8] and Paraschivoiu [9])) have resorted to these
or similar models; the results presented in this paper using URANS are thus a link between
previous research and the application of more complex models such as LES and DES.

Figure 8. Vorticity field at θ = 90°, Large Eddy Simulation.

![Figure 8: Vorticity field at θ = 90°, Large Eddy Simulation](../images/vj5-fig8.jpg)

Figure 9. Vorticity field at θ = 120°, Large Eddy Simulation.

![Figure 9: Vorticity field at θ = 120°, Large Eddy Simulation](../images/vj5-fig9.jpg)

### 4.3 DES

Comparing with the experimental results, the S-A model underestimates the generation and
shedding of vorticity at the leading edge (in the simulation the leading edge shed vorticity
is only located in the first half of the airfoil while experimental results show it covering the
entire airfoil length - Figure 2); it is also unable to predict the roll-up of the trailing edge shed
vorticity clearly seen in the experimental work (Figure 3) even at  = 120. The k- model
(Figures 6 and 7), although more computationally expensive, is also not able to predict these
two main phenomena of the flow field. The option of both models of simulating all scales of
turbulence based on the Boussinesq hypothesis of isotropy of the turbulence clearly proved to be
insufficient for this flow.

Figure 10. Vorticity field at θ = 90°, Detached Eddy Simulation.

![Figure 10: Vorticity field at θ = 90°, Detached Eddy Simulation](../images/vj5-fig10.jpg)

Figure 11. Vorticity field at θ = 120°, Detached Eddy Simulation.

![Figure 11: Vorticity field at θ = 120°, Detached Eddy Simulation](../images/vj5-fig11.jpg)

## 5. Comparison of Force Simulation

In this work the comparison of the results is made by comparing the tangential and normal
forces on the blade, as the forces are related to the power production and loads on the rotor.
The force coefficients for the blade are compared for the different turbulence models, as well as
the influence of the grid refinement. The figures show that the force peaks are different between
the models, and that the higher frequency oscillations are more apparent for the DES and LES
models.

Figure 12. Tangential and normal force in the blade, SA model, Δt = 1/2°/ω. Instantaneous values over three rotations.

![Figure 12: Tangential and normal force in the blade, SA model, Δt = 1/2°/ω](../images/vj5-fig12.jpg)

Figure 13. Tangential and normal force in the blade, k-ε model, Δt = 1/2°/ω. Instantaneous values over three rotations.

![Figure 13: Tangential and normal force in the blade, k-ε model, Δt = 1/2°/ω](../images/vj5-fig13.jpg)

Figure 14. Tangential and normal force in the blade, DES, Δt = 1/4°/ω. Instantaneous values over five rotations.

![Figure 14: Tangential and normal force in the blade, DES, Δt = 1/4°/ω](../images/vj5-fig14.jpg)

Figure 15. Tangential and normal force in the blade, LES model, Δt = 1/4°/ω. Instantaneous values over four rotations.

![Figure 15: Tangential and normal force in the blade, LES model, Δt = 1/4°/ω](../images/vj5-fig15.jpg)

## 6. Verification to Grid Sensitivity

Figures 16 and 17 show the vorticity distribution at θ = 90°. Similarly to what it was
observed by Simao Ferreira et al [4] with a Laminar model, also for the DES model the first
refinement of the time step (Δt = 1/8*ω^-1) results in a convergence of the vorticity and an
early roll-up of the wake at the trailing edge; yet, the second refinement (Δt = 1/16*ω^-1) does
not consecutively generate another increase: in fact the differences between the two results are
minimal and in what is expected in relation to the randomness of the flow. This interpretation
of the results is also confirmed by the simulated force values (Figure 18). The DES simulation
appears to be less sensitive to time grid refinement at this magnitude of step size.

### 6.1 Time Grid Refinement

In the reference simulation, a time step Δt = 1/4ω^-1 is used. The analysis now presented
compares this simulation with two other with the same initial conditions but time steps
Δt = 1/8ω^-1 and Δt = 1/16ω^-1.
\Delta t = 1/8\omega^{-1} and \Delta t = 1/16\omega^{-1}.

Figure 16. Vorticity field at θ = 90°, Δt = 1/8°/ω.

![Figure 16: Vorticity field at θ = 90°, Δt = 1/8°/ω](../images/vj5-fig16.jpg)

Figure 17. Vorticity field at θ = 90°, Δt = 1/16°/ω.

![Figure 17: Vorticity field at θ = 90°, Δt = 1/16°/ω](../images/vj5-fig17.jpg)

Figure 18. Effect on tangential and normal force of change of the time grid refinement.

![Figure 18: Effect on tangential and normal force of change of the time grid refinement](../images/vj5-fig18.jpg)

### 6.2 Space Grid Refinement

The work of Simao Ferreira et al [4] presented an evaluation of the effect of space and time
grid refinement/coarsening for the case of a Laminar model; such evaluation showed a high
sensitivity of the results to the refinement of the grid. Yet, the DES model has proved to be a
more suitable simulation tool; thus, in this section, we shall evaluate the robustness of the DES
simulation towards grid refinement.

Figure 19. Vorticity field at θ = 90°, Δt = 0.25°/ω, 2 times coarser grid.

![Figure 19: Vorticity field at θ = 90°, Δt = 0.25°/ω, 2 times coarser grid](../images/vj5-fig19.jpg)

Figure 20. Vorticity field at θ = 90°, Δt = 0.25°/ω.

![Figure 20: Vorticity field at θ = 90°, Δt = 0.25°/ω](../images/vj5-fig20.jpg)

Figure 21. Effect on tangential and normal force of change of the space grid refinement.

![Figure 21: Effect on tangential and normal force of change of the space grid refinement](../images/vj5-fig21.jpg)

## 7. Verification Convergence Error

The results showed in Figures 19, 20 and 21 shows that the overgeneration of vorticity and
is also present when using a DES model; however, the variation is not as large as observed in
the laminar model and the effect on the force is small.

To observe the validity of the latter, three simulations of a half rotation starting at the same
initial condition are compared (Figure 22). The three solutions encompass:

Figure 22. The effect of convergence on tangential and normal force of change of the convergence iteration.

![Figure 22: The effect of convergence on tangential and normal force of change of the convergence iteration](../images/vj5-fig22.jpg)

## 8. Conclusions

The results show the suitability of the PIV data for the validation of the model, the need
for accurate simulation of the large eddies and the sensitivity of the model to grid refinement.

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
