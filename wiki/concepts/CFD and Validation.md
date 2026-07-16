---
Created: 2026-07-01
Updated: 2026-07-16
Sources:
  - "[[va10]]"
  - "[[vj5]]"
  - "[[vj6]]"
  - "[[va11]]"
  - "[[va13]]"
  - "[[va15]]"
  - "[[va14]]"
  - "[[vj13]]"
  - "[[vj15]]"
  - "[[vj17]]"
  - "[[va17]]"
  - "[[va18]]"
  - "[[va21]]"
  - "[[vj18]]"
  - "[[va25]]"
  - "[[va26]]"
  - "[[va27]]"
  - "[[vj11]]"
  - "[[vj26]]"
  - "[[va9]]"
  - "[[vj2]]"
  - "[[vj29]]"
  - "[[cj1]]"
  - "[[cj2]]"
  - "[[cj3]]"
  - "[[cj4]]"
  - "[[cj9]]"
  - "[[cj10]]"
  - "[[ca33]]"
  - "[[fa1]]"
Source_count: 30
tags:
  - concepts
---
## CFD and Validation

This page covers the simulation workflow used to check a VAWT before hardware is built.

- CFD is used to compare concepts, test geometry changes, and estimate torque and power coefficient. (source: sources/vj2.md, sources/vj5.md, sources/vj6.md)
- Mesh refinement matters. (source: sources/vj5.md, sources/vj6.md)
- The va10 review recommends explicit grid-independence and domain-size sensitivity checks before trusting performance outputs. (source: sources/va10.md)
- It says cells should be clustered near the blade and wake, with wall-adjacent resolution chosen to match the turbulence model's wall treatment. (source: sources/va10.md)
- PIV data is a useful validation target for VAWT CFD. (source: sources/vj5.md)
- The CFD review says 3-D models usually capture losses better than 2-D models. (source: sources/vj6.md)
- The review also uses torque, power coefficient, flow separation, and wake dynamics as key outputs. (source: sources/vj6.md)
- It reports that PISO outperformed SIMPLE and COUPLED in one reviewed Darrieus CFD comparison. (source: sources/va10.md)
- It also treats transition SST, LES, and hybrid RANS-LES as important when separation and unsteady wake fidelity matter more than design-stage speed. (source: sources/va10.md)
- The va11 wake review adds that PIV-validated 2-D and 3-D CFD were both used for wake studies, but 3-D simulation was needed to capture blade-tip vortices and avoid over-predicting H-rotor performance. (source: sources/va11.md)
- It also reviews RANS, LES, DES, and analytical wake-model development as complementary validation layers for wake prediction. (source: sources/va11.md)
- The va13 building-integration study uses ANSYS Fluent with the SST `k-ω` model to compare rooftop turbine cases, but it explicitly says mesh sensitivity and experimental validation were not included in that study. (source: sources/va13.md)
- The va15 experiment adds scarce low-`lambda`, time-accurate startup data that the paper explicitly positions as future validation material for numerical models. (source: sources/va15.md)
- The va14 study adds a validated 2D URANS parameter sweep using transition SST (`γ-Reθ`), sliding mesh, grid-sensitivity analysis, and two separate experimental comparisons. (source: sources/va14.md)
- The vj13 study uses 2-D transient CFD in Fluent with `k-ω SST`, grid and time-step independence checks, and validation against wind-tunnel data within about 5% error. (source: sources/vj13.md)
- It also implements the variable rotational speed strategy through a UDF and a pressure-based coupled solver with second-order upwind discretization. (source: sources/vj13.md)
- The vj15 study uses 2-D transient CFD with SST `k-omega` and a UDF-driven variable-pitch motion law to compare harmonic pitch functions. (source: sources/vj15.md)
- The vj17 study verifies its optimized Savonius geometry with CFD after DVM/SSA optimization and uses a 3D domain with SST `k-omega` for the final comparison. (source: sources/vj17.md)
- The va17 rooftop-siting thesis adds a building-scale CFD use case: screening candidate roof edges and then recommending follow-up anemometer measurements instead of treating the simulation alone as sufficient validation. (source: sources/va17.md)
- The va18 urban-resource paper validates a CFD-based siting workflow against two local met towers, comparing mean wind speed, wind power density, and Weibull-based wind-distribution shape between measured and reconstructed site statistics. (source: sources/va18.md)
- It reports that local climatology assimilation best matched the measured site-to-site ratios, while background assimilation, TopoWind transfer, and MCP normalization still preserved the ranking of the two sites. (source: sources/va18.md)
- The va21 rooftop prototype paper adds a direct experiment-versus-simulation comparison for an installed machine, using ANSYS Fluent `16.2`, a transient double-precision parallel solver, and a `k-epsilon` turbulence model on a simplified rotor section. (source: sources/va21.md)
- It reports a mesh-sensitivity check across coarse, fine, and extra-fine meshes, and says the fine and extra-fine meshes produced nearly identical rotor speed, angular velocity, and torque at `3.5 m/s`, so the fine mesh was retained. (source: sources/va21.md)
- The same source reports less than `10%` deviation in rotor speed and less than `20%` deviation in voltage and power relative to measured data, while explicitly attributing part of the remaining error to simplified blade geometry and `2D` modeling of a `3D` turbine. (source: sources/va21.md)
- The vj18 review says many variable-design results are still simulation-heavy and calls for more wind-tunnel and real-world testing before commercialization claims are trusted. (source: sources/vj18.md)
- It treats validation as especially important for complex active systems such as variable pitch, flap control, and synthetic jets. (source: sources/vj18.md)
- The va25 airfoil study adds a `2D` URANS CFD workflow with SST `k-omega`, sliding mesh, grid-independence analysis, and GCI, validated against published experimental data with less than `5%` maximum `Cp` error for the reference rotor. (source: sources/va25.md)
- It also places the inlet and outlet much farther from the rotor than many wind-tunnel-style setups, explicitly to suppress solid blockage and allow more open-field-like wake development. (source: sources/va25.md)
- The va26 pitch-angle study adds a high-fidelity `2D` URANS workflow with transition SST, extensive sensitivity checks on revolutions, grid and azimuthal increment, and two validation studies against wake and power-coefficient data. (source: sources/va26.md)
- That source explicitly ties observed CFD disagreement to missing blade-tip losses, absent strut/tower drag in `2D`, and the inability of `2D` URANS to capture some `3D` dynamic-stall and blade-wake effects. (source: sources/va26.md)
- The va27 airfoil-shape study adds a very large transient CFD campaign, `252` simulations, based on URANS for `126` symmetric airfoils at `lambda = 2.5` and `3.0`, with three validation studies used to justify the setup. (source: sources/va27.md)
- It uses the same CFD framework to map the coupled influence of thickness, thickness position, and leading-edge radius in deep dynamic stall, rather than validating only one chosen shape. (source: sources/va27.md)

The VAWT review says URANS with `k-ω SST` is the main design-stage tool, while transition SST and DES/LES are preferred when dynamic stall fidelity matters most. (source: sources/vj11.md)
It reports that 2-D URANS can overpredict Cp by 15-30% relative to validated 3-D simulations. (source: sources/vj11.md)
It also recommends practical setup ranges of about 15D upstream, 10D downstream, 20D lateral extent, and 20-30 revolutions before sampling. (source: sources/vj11.md)

The vj26 review adds a broader caution that turbulence-model choice has a strong effect on VAWT torque prediction, so CFD setup details materially affect the answer rather than only its precision. (source: sources/vj26.md)
It also says CFD gives useful insight into steady operation and comparative rotor behavior, but cited startup studies still found poor reliability during the startup transient when compared against experiments. (source: sources/vj26.md)

The `vj29` H-rotor review reinforces that `RANS` / `URANS` formulations dominate the literature, with `k-omega SST` the single most common turbulence model in its survey. (source: sources/vj29.md)
- It says `2D` simulations are still appropriate for early design, airfoil comparison, and trend analysis, but they neglect tip losses and spanwise flow and can overpredict `Cp` by anything from under `15%` in well-tuned cases to roughly `30%-40%` in optimistic ones. (source: sources/vj29.md)
- The same source says `3D` simulations are required for reliable absolute-performance prediction, blade loading, wake interaction, and farm-level studies, though at much higher computational cost. (source: sources/vj29.md)
- It also argues that validation should compare more than a single `Cp-TSR` curve and should include wake vortices, pressure fields, dynamic-stall signatures, and vorticity fields when possible. (source: sources/vj29.md)

The va9 paper says its sliced DMS approach can be integrated into existing CFD and CAD tools to improve analysis of complex Darrieus blade-form designs. (source: sources/va9.md)
It also compares streamtube, vortex, and cascade models, noting that vortex models have high experimental correlation with the latest improvements but take the highest computation time among the listed prediction models. (source: sources/va9.md)

The hybrid-rotor CFD paper in `vj2` uses 3D SolidWorks Flow Simulation rather than 2D analysis because the authors say the vortex-like structures in the rotor require a full 3D domain. (source: sources/vj2.md)
It reports a computational domain of 15 m by 12 m by 12 m, 7 m/s inlet wind speed, 5% turbulence intensity, and torque samples at nine attack angles from 0 degrees to 120 degrees. (source: sources/vj2.md)

The `cj1` paper compares a scaled isolated turbine against CFD but does not experimentally validate its planetary cluster; it also states that 2D CFD cannot investigate trailing vortices and tip losses. (source: sources/cj1.md)

The `cj2` paper adds a 3D transient Fluent setup for a 12-blade Farrah VAWT, and its grid study shows that splitting the 12 blades into separate wall boundaries materially changes predicted power relative to treating them as one connected wall. (source: sources/cj2.md)
It reports that `k-omega SST` produced a usable torque history and about `4.02%` error for its chosen comparison, while Spalart-Allmaras gave a minimum reported error of `43.25%` and did not reproduce the expected sinusoidal torque signal. (source: sources/cj2.md)
It also shows a validation caveat that matters beyond this one rotor: the CFD-versus-experiment agreement depends on assumed mechanical losses of `50%` or `20%`, so the result is better treated as calibrated trend agreement than direct validation of raw power. (source: sources/cj2.md)
The paper itself recommends transition SST for future work because its fully turbulent setup may overestimate power in the transitional Reynolds-number range it studies. (source: sources/cj2.md)

The `cj3` transcript adds a teaching-oriented validation workflow: build the Darrieus setup from a reference paper, digitize reference `Cp` data with `WebPlotDigitizer`, compute a time step from turbine data, and compare after averaging the last cycle. (source: sources/cj3.md)
Its stated error is below `1.38%`, but because the source is a promotional transcript without the full reference citation or full Fluent setup, it supports the workflow outline more strongly than the quantitative validation claim itself. (source: sources/cj3.md)

The `cj4` SimScale tutorial adds a more practical beginner-validation mindset: use CFD post-processing to locate strong wake or pressure regions, then compare those locations against sensor measurements in a wind tunnel or field test if possible. (source: sources/cj4.md)
Because the source is only a quick tutorial transcript with default meshing and no reported benchmark dataset, it supports the idea of validation-by-measurement more than any specific quantitative CFD claim. (source: sources/cj4.md)

The `cj9` paper adds a useful isolated-airfoil validation target for low-Re VAWT work: `NACA0018` measured in a low-turbulence tunnel from `Re = 30,000` to `160,000`, with two independent lift-measurement methods agreeing strongly across most of the tested range. (source: sources/cj9.md)
It also adds a model-comparison caution that matches the repo's broader theme: `XFOIL` follows the general low-Re trends reasonably well but overestimates maximum lift, while `2-D` Transition SST predicts the drag rise better but underestimates lift at `Re = 160,000`. (source: sources/cj9.md)

The `cj10` SimScale validation case adds a documented high-Re airfoil benchmark pattern: pseudo-`2D` single-cell extrusion, Standard meshing, `k-omega SST`, full near-wall resolution at `y+ ~ 1`, and angle of attack imposed through inlet velocity components. (source: sources/cj10.md)
It also makes explicit that a stable, accurate-looking validation case can still need numerics tuning, in this case changing velocity and pressure-gradient interpolation schemes from `Least Squares` to `Gauss-Linear`. (source: sources/cj10.md)

The `ca33` airfoil tutorial provides a sectional-airfoil validation sequence: match airfoil, Reynolds number, and angle of attack; use freestream-aligned coefficient axes; inspect convergence and solved wall `y+`; then compare lift and drag with the matching published coefficient data. (source: sources/ca33.md)
Its worked result is at `Re = 6 x 10^6` for a NACA 4415 in 2D, so it is not direct validation evidence for a three-dimensional NACA 0018 case at `Re = 50,000`. (source: sources/ca33.md)

The `fa1` finite-wing reference explains why a finite-span validation model cannot be compared directly with a two-dimensional airfoil polar: exposed tips create vortices, downwash, reduced effective angle of attack, lower lift, and induced drag. (source: sources/fa1.md)

![Source figure](va10-fig5.jpg)
Original caption: Fig. 5. Computational grid independency study [31]. [[va10|Source]]
![Source figure](va11-fig25.jpg)
Original caption: Fig. 25. Vorticity magnitudes in the blade mid-span and vertical planes (units, 1/s) [52]. [[va11|Source]]
![Source figure](va13-fig7.jpg)
Original caption: Figure 7. Computational domain and mesh setup. [[va13|Source]]
![Source figure](va17-fig6.jpg)
Original caption: Figure 6. Navier-Stokes Equations employed by the CFD program. [[va17|Source]]
![Source figure](va18-fig13.jpg)
Original caption: Figure 13: Mean Wind Power Density (W/m2), Horizontal section 20m above the ground; Mean Wind Power Density (W/m2), Vertical cross-section through MT1 and MT2; Mean Turbulence Intensity, Vertical cross-section through MT1 and MT2. [[va18|Source]]
![Source figure](va14-table2.jpg)
Original caption: Table 2. Comparison between the measured CP [81] and simulated CP (present CFD study). [[va14|Source]]
![Source figure](va21-fig22.jpg)
Original caption: Figure 22. Comparison between computed and measured parameters: (a) rotor speed, (b) DC voltage and (c) power (source: Authors' elaboration). [[va21|Source]]
![Source figure](va25-fig8.jpg)
Original caption: Fig. 8 Reference model (NACA0021) validation and verification. [[va25|Source]]
![Source figure](va27-fig14.jpg)
Original caption: Fig. 14. Turbine CP in t/c - xt/c space. Each contour plot is based on 42 simulations. Note the difference in range of colormaps. [[va27|Source]]
![Source figure](va26-fig10.jpg)
Original caption: Fig. 10. Comparison of calculated power coefficient against experimental and numerical data by Castelli et al. [69]. [[va26|Source]]

Related:
- [[Optimization]]
- [[Dynamic Stall]]
- [[Wind Tunnel Testing]]
- [[Double-Multiple Streamtube Model]]
- [[Architectural Wind Turbines]]
- [[Climatology Assimilation]]
- [[va21 Rooftop Vertical-Axis Wind Turbine]]
- [[Variable VAWT Design]]
- [[va25 Reference H-Rotor Darrieus VAWT]]
- [[va27 Reference One-Bladed H-Type VAWT]]
- [[va26 3-Bladed H-Type VAWT]]
- [[cj2 Farrah VAWT CFD Setup]]
- [[cj3 Darrieus Course CFD Workflow]]
- [[cj4 SimScale Savonius Workflow]]
- [[cj9 NACA0018 Low-Re Validation Data]]
- [[cj10 SimScale NACA0012 High-Re Validation]]
