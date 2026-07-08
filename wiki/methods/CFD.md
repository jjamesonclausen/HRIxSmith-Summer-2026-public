---
Created: 2026-06-25
Updated: 2026-07-07
Sources: [[n1]], [[HRI2526]], [[vj12]], [[vj2]], [[vj5]], [[vj6]], [[va10]], [[va11]], [[va13]], [[va17]], [[va18]], [[va20]], [[va21]], [[va22]], [[va25]], [[va26]], [[va27]], [[va14]], [[va4]], [[va7]], [[vj20]], [[vj27]], [[vj8]]
Source_count: 23
Tags: #methods
---
## Computational Fluid Dynamics (CFD)

Numerical method for simulating fluid flow by dividing the domain into discrete cells. (source: sources/n1.md, sources/va1.md)

- Used to model wind flow and turbine performance. (source: sources/n1.md)
- Requires careful setup, boundary conditions, and mesh quality. (source: sources/n1.md)
- The HRI report used SimScale with stationary and rotating domains and a k-omega SST turbulence model. (source: sources/HRI2526.md)
- The workflow validated CFD against a NACA 0012 airfoil and a classical Savonius before analyzing the selected helical hybrid. (source: sources/HRI2526.md)
- The selected helical hybrid reported Cp 0.19 at TSR 1 in CFD. (source: sources/HRI2526.md)
- The vj12 review treats CFD as the main way to study counter-rotation, blade-profile changes, deflectors, and site/layout effects when experiments are not practical. (source: sources/vj12.md)
- It says one deflector study used URANS with the k-omega turbulence model as the main analysis tool. (source: sources/vj12.md)
- It reinforces that CFD sits alongside field and lab testing for VAWT review work, not as a replacement for measurements. (source: sources/vj12.md)
- Used in a SolidWorks Flow Simulation study of a Savonius-Darrieus hybrid rotor with a 3D domain, mesh refinement, and nine attack angles from 0 to 120 degrees. (source: sources/vj2.md)
- The same hybrid-rotor paper reports a 15 m by 12 m by 12 m domain, 7 m/s inlet wind speed, 5% turbulence intensity, and the Lam and Bremhorst modified `k-epsilon` model. (source: sources/vj2.md)
- A dynamic-stall study on a single-bladed 2D VAWT compared URANS, LES, and DES; DES matched PIV vorticity data best. (source: sources/vj5.md)
- That paper found grid refinement and convergence settings materially affected vorticity and force predictions. (source: sources/vj5.md)
- A later review organized VAWT CFD around problem definition, meshing, equation discretisation, boundary conditions, numerical solution, and post-processing. (source: sources/vj6.md)
- That review also emphasized static/dynamic meshing, turbulence-model choice, near-wall resolution, and experimental validation. (source: sources/vj6.md)
- It framed CFD as the detailed middle ground between lower-fidelity models and wind-tunnel experiments. (source: sources/vj6.md)
- The va10 review recommends grid-sensitivity and domain-sensitivity studies, clustering cells near the blade and wake, and matching `y+` to the wall treatment used by the turbulence model. (source: sources/va10.md)
- It reports a reviewed domain-size study where torque stabilized when the domain-to-rotor-diameter ratio exceeded 15, and it cites about 14 diameters of downwind length as enough for wake development. (source: sources/va10.md)
- It compares `k-epsilon`, `k-omega SST`, transition SST, LES, and hybrid RANS-LES, and frames LES and hybrid RANS-LES as higher-fidelity options for separated unsteady flow at higher computational cost. (source: sources/va10.md)
- In one reviewed solver comparison, PISO produced the best results while SIMPLE struggled at low TSR and COUPLED failed to capture the blade-flow behavior. (source: sources/va10.md)
- The va11 wake review adds wake-specific uses of RANS, LES, and DES, including PIV-validated simulations of asymmetric wake spreading, counter-rotating vortices, and blade-tip effects. (source: sources/va11.md)
- It says 2-D wake CFD misses blade-tip vortices and therefore over-predicts H-rotor performance relative to 3-D simulation. (source: sources/va11.md)
- It also reviews actuator-based LES approaches such as actuator line and actuator swept-surface models for reducing computational cost in large wake studies. (source: sources/va11.md)
- The va13 study uses SolidWorks for turbine geometry, ANSYS Fluent with the SST `k-ω` turbulence model for aerodynamic comparison, and case-specific rooftop domains and meshes for the three designs. (source: sources/va13.md)
- It reports node and element counts for each case but explicitly leaves mesh-sensitivity and experimental validation for future work because the study's main goal was building-scale energy and economic analysis. (source: sources/va13.md)
- The va17 thesis uses PHOENICS CFD as a building-siting tool rather than a rotor-performance tool, comparing roof-edge speed-up regions on Eastgate and Johnson Athletic Center under a 4.9 m/s prevailing-wind case. (source: sources/va17.md)
- It uses the CFD output to reject Eastgate as impractical for edge mounting and to recommend follow-up measurements at Johnson's west roof edge. (source: sources/va17.md)
- The va18 campus-resource paper uses UrbaWind RANS CFD with a `k-L` turbulence framework, about 4 to 5 million cells, 1 m near-site resolution, and 12 directional runs to map urban speed-up, turbulence, and wind-power-density structure. (source: sources/va18.md)
- The same source also uses TopoWind to transfer remote airport climatology toward the site before applying the local urban CFD workflow. (source: sources/va18.md)
- The va20 study uses ANSYS Fluent with a realizable `k-epsilon` turbulence model, SIMPLE pressure-velocity coupling, a sliding mesh, and second-order upwind discretisation to compare three VAWT configurations for low-wind urban use. (source: sources/va20.md)
- It reports tetrahedral meshes with roughly `405,679`, `437,894`, and `1,147,223` elements for the C-blade, involute, and involute-plus-WFM cases respectively. (source: sources/va20.md)
- The va21 rooftop prototype paper uses ANSYS Fluent `16.2` with a transient double-precision parallel solver, a `k-epsilon` turbulence model, hybrid initialization, and `1000` time steps of `0.01 s`. (source: sources/va21.md)
- It models a simplified rotor section inside rotating and stationary zones with selected element sizes of `2 mm` and `20 mm`, after a mesh-sensitivity comparison against coarser and finer alternatives. (source: sources/va21.md)
- That source uses CFD as a validation companion to the installed prototype, comparing computed rotor speed, voltage, and power against measured data instead of treating simulation alone as sufficient. (source: sources/va21.md)
- The va22 paper uses `2D` CFD to generate lift and drag coefficients for a low-TSR helical-VAWT design method, rather than to predict the whole rotor directly with full `3D` CFD. (source: sources/va22.md)
- It reports a `15D x 7D` flow domain, `1,162,500` nodes, `575,142` elements, maximum `y+ = 2.86`, `9 m/s` inlet velocity, `18%` turbulence intensity, `170 rpm` rotor speed, and an SST turbulence model in transient URANS. (source: sources/va22.md)
- The same source uses time steps corresponding to `1 degree` of rotor rotation, about `9.8 x 10^-4 s`, and then feeds the resulting airfoil-force data into the mathematical power model. (source: sources/va22.md)
- The va25 study uses `2D` incompressible URANS in ANSYS Fluent with SST `k-omega`, sliding mesh, SIMPLE coupling, second-order schemes, and a time step corresponding to `1 degree` azimuth increments. (source: sources/va25.md)
- It reports a very large computational domain (`97D x 78D`) with a `1.5D` rotating region, selected so solid blockage stays below about `0.32%` and test-section speed increase remains below about `1%`. (source: sources/va25.md)
- The same source performs grid-independence analysis across four meshes, calculates GCI between its medium and fine grids, and selects a roughly `0.49 million`-cell mesh as the approved grid for the study. (source: sources/va25.md)
- The va26 study uses `2D` URANS in ANSYS Fluent `16.1` with the 4-equation transition SST model, SIMPLE coupling, second-order spatial and temporal schemes, and a `0.1 degree` azimuth increment for the unsteady turbine runs. (source: sources/va26.md)
- It reports a low-solidity H-rotor domain with a `1.5d` rotating core inside a `30d x 20d` fixed domain, a `5%` blockage ratio, and data sampling after `20` revolutions with averaging over the next `10`. (source: sources/va26.md)
- The same source also performs separate static-airfoil CFD at `Re = 1.15 x 10^5` to identify the static stall angle and compare static and dynamic load behavior. (source: sources/va26.md)
- The va27 study uses high-fidelity transient CFD to evaluate `126` symmetric airfoil shapes in a one-bladed H-type VAWT, with URANS and the transition SST model chosen from prior turbulence-model benchmarking work by the authors. (source: sources/va27.md)
- It reports a computational domain of `30d x 30d`, `302,815` quadrilateral cells, `800` cells around the airfoil circumference, and `max y+ < 2.5`, together with `20` turbine revolutions to reach convergence. (source: sources/va27.md)
- The same source performs three validation studies and uses the resulting framework to study deep dynamic stall rather than only the near-optimal operating regime. (source: sources/va27.md)
- The va14 study uses 2D URANS with the transition SST (`γ-Reθ`) model, a sliding mesh interface, about 400,000 quadrilateral cells, and a grid-sensitivity analysis quantified with GCI. (source: sources/va14.md)
- It validates against wake-velocity data for a 2-bladed turbine and power-coefficient data for a 3-bladed turbine before running the larger parametric sweep. (source: sources/va14.md)
- The helical-VAWT study used 2D LES for blade-scale flow and 3D U-RANS with SST k-omega for the full rotor. (source: sources/va4.md)
- It found that 3D effects such as tip vortex and second flow reduce performance relative to 2D predictions. (source: sources/va4.md)
- A helical-VAWT helix-angle study used Ansys FLUENT with stationary and rotating domains, a sliding mesh interface, transition SST k-omega turbulence modeling, grid/time-step independence checks, and validation against McLaren's experimental VAWT data. (source: sources/va7.md)
- That study used z-vorticity contours and wake profiles to connect section-wise blade loading, vortex shedding, wake interaction, and flow separation to moment-coefficient behavior. (source: sources/va7.md)
- The vj20 paper uses a sliding-mesh URANS workflow with a `k-epsilon` turbulence model, about `14.5D` streamwise domain size, symmetry sidewalls, pressure outlet, and wall treatment on the blades and shaft. (source: sources/vj20.md)
- It reports more than `2 million` mesh elements, `15` inflation layers, element length `0.005 m` at the interface, no meaningful `Cp` change beyond refinement level `2` (`321,189` nodes in the reported MIT), and a chosen time step of `0.05 s`. (source: sources/vj20.md)
- The `vj27` review adds that deflector studies commonly rely on commercial CFD plus URANS, and it specifically cites `k-omega` / URANS for one airfoil-shaped Savonius-deflector study and `3D` CFD for flat-plate deflector studies. (source: sources/vj27.md)
- It also emphasizes that many deflector concepts still lack enough real-time experiments, so CFD-heavy gains should be treated as promising rather than fully mature. (source: sources/vj27.md)

## Figures

![Source figure](va4-fig11.jpg)
Original caption: Figure 11. The streamlines at 60◦, 90◦, 150◦, 180◦, (a–c) corresponding to the results at TSR 0.9, 1.46 and 2.3 respectively, red frames represent the wake vortex generated from another blade. [[va4|Source]]
![Source figure](va4-fig14.jpg)
Original caption: Figure 14. Power coefficient results derived by 2D LES and 3D U-RANS methods for Rec = 60,800, TSR = 1.46. [[va4|Source]]
![Source figure](va7-fig2.jpg)
Original caption: Figure 3. (a) Sectional view of the domain mesh: (b) mesh near the blade, (c) mesh growth surrounding the blade. [[va7|Source]]
![Source figure](va7-fig21.jpg)
Original caption: Figure 21. Z-vorticity magnitude of 90◦helical-bladed VAWT at 100◦, 130◦, and 150◦of azimuth angles of rotation of a [[va7|Source]]
![Source figure](va10-fig4.jpg)
Original caption: Fig. 4. Structured computational grid around blade [25]. [[va10|Source]]
![Source figure](va10-fig5.jpg)
Original caption: Fig. 5. Computational grid independency study [31]. [[va10|Source]]
![Source figure](va10-fig7.jpg)
Original caption: Fig. 7. Lift coefficient comparison for transition SST and k omega SST turbulence models. Adapted from [32]. [[va10|Source]]
![Source figure](va10-fig8.jpg)
Original caption: Fig. 8. Comparison of power coefficient at different tip speed ratios for IDDES and k omega SST turbulence models [53]. [[va10|Source]]
![Source figure](va11-fig25.jpg)
Original caption: Fig. 25. Vorticity magnitudes in the blade mid-span and vertical planes (units, 1/s) [52]. [[va11|Source]]
![Source figure](va11-fig26.jpg)
Original caption: Fig. 26. Vorticity magnitudes in the top blade-tip and vertical planes (units, 1/s) [52]. [[va11|Source]]
![Source figure](va13-fig7.jpg)
Original caption: Figure 7. Computational domain and mesh setup. [[va13|Source]]
![Source figure](va17-fig11.jpg)
Original caption: Figure 11. Wind velocity profile around Johnson Athletic Center. [[va17|Source]]
![Source figure](va18-fig2.jpg)
Original caption: Figure 2: Unstructured Cartesian meshing grid. [[va18|Source]]
![Source figure](va20-fig7.jpg)
Original caption: Figure 7. Computational domain defined in ANSYS design modeler. [[va20|Source]]
![Source figure](va14-fig1.jpg)
Original caption: Fig. 1. Schematic of (a) the reference turbine, (b) computational domain (both not to scale); (c-e) computational grid near the (c) rotating core, (d) airfoil, and (e) trailing edge. [[va14|Source]]
- The CRVAWT optimization paper used STAR-CCM+ CFD, validated an isolated VAWT against wind-tunnel data, and then used the simulation outputs in a response-surface optimization workflow. (source: sources/vj8.md)

![Source figure](vj12-fig21.jpg)
Original caption: Figure 21: Schematic view and CFD streamlines for flow around a flanged diffuser [110]. [[vj12|Source]]
![Source figure](vj2-fig4a.jpg)
Original caption: Figure 4: Turbulent flow due to the Savonius rotor for an angle of attack of 30 degrees: (a) - side view; (b) - top view [[vj2|Source]]
![Source figure](vj2-fig4b.jpg)
Original caption: Figure 4: Turbulent flow due to the Savonius rotor for an angle of attack of 30 degrees: (a) - side view; (b) - top view [[vj2|Source]]

#methods
