---
Created: 2026-07-20
Sources:
  - sources/vj20.md
  - sources/HRI2526.md
  - SimScale documentation
tags:
  - cfd
  - simscale
  - validation
  - vj20
---

# vj20 SimScale Validation Study

## Scope And Source Limits

This is a three-dimensional, transient validation workflow for the scaled hybrid H-VAWT in `vj20`. It recreates the reported physical condition in SimScale, but cannot exactly reproduce the original numerical model because `vj20` used ANSYS Fluent rather than SimScale. (source: sources/vj20.md)

The repository does not contain a source named `HRI2525`; this note uses `HRI2526` as the intended HRI reference. (source: sources/HRI2526.md)

## 1. Define The Validation Case

1. Use the scaled `vj20` geometry.
   - Outer rotor: three NACA0018 blades; diameter `0.350 m`, height `0.283 m`, chord `0.0496 m`, and pitch `-2.82 degrees`.
   - Inner rotor: three DU 06-W-200 blades; diameter `0.143 m`, height `0.146 m`, chord `0.0497 m`, and pitch `-3.41 degrees`.
   - Space outer blades `120 degrees` apart and offset the inner rotor by `60 degrees`. (source: sources/vj20.md)
2. Start with inlet velocity `3.63 m/s` and `TSR = 3`. `vj20` reports an experimental peak `Cp = 0.478` at this condition and elsewhere reports a computational peak `Cp = 0.486`; retain both values as separate comparison targets. (source: sources/vj20.md)
3. Calculate prescribed angular velocity from TSR rather than copying the paper's scaled-speed table:

```text
omega = TSR * U_infinity / R_outer
      = 3 * 3.63 / 0.175
      = 62.2 rad/s
```

The table's scaled `37.06 rad/s` does not produce TSR 3 with the table's scaled diameter and wind speed, so it is source-internally inconsistent. (source: sources/vj20.md)

## 2. Import And Prepare CAD

1. Create a project and upload the STEP geometry.
2. Confirm the geometry uses metres and the outer diameter is `0.350 m`.
3. Retain blade and central-shaft solids. Do not include tunnel brackets, bearings, generator, or other test rig hardware in the baseline; `vj20` explicitly states wall conditions for blades and the central shaft. (source: sources/vj20.md)
4. Preserve selectable surface groups for outer blades, inner blades, and shaft. This permits component-level torque controls.
5. In CAD Mode, run an interference check and correct overlaps before creating the flow volume. Overlapping CAD bodies can prevent successful operations and meshing. (source: https://www.simscale.com/docs/cad-preparation/cad-mode/)

## 3. Create External Flow Volume

1. In CAD Mode choose **Create > Flow volume > External**.
2. Use global axes: `+X` inflow, `+Z` shaft axis, and the shaft midpoint as `(0, 0, 0)`.
3. For the initial credible baseline, set the outer domain extents from the shaft center:
   - `X min = -3.50 m` (`15D` upstream)
   - `X max = +5.25 m` (`10D` downstream)
   - `Y min/max = -3.50 m / +3.50 m` (`20D` width)
   - `Z min/max = -3.50 m / +3.50 m`
4. This is intentionally larger than the `14.5D` streamwise domain reported by `vj20`. The HRI best-practice appendix and the validated H-rotor study support `10-15D` upstream, at least `10D` downstream, and `20D` width to limit artificial-boundary effects. (source: sources/vj20.md, sources/HRI2526.md, sources/va32.md)
5. Confirm the resulting volume is air around the turbine, with rotor solids excluded from the fluid.

## 4. Create Rotating Cylinder

1. In CAD Mode choose **Create > Cylinder > Custom**.
2. Set center `(0, 0, 0)`, axis `(0, 0, 1)`, radius `0.2625 m`, and height `0.50 m`.
3. This creates a `1.5D`-diameter rotating fluid zone around the outer rotor. It is a supported starting point from validated H-rotor work, not a universal optimum. (source: sources/va32.md)
4. Ensure the cylinder is closed, coaxial with the shaft, fully inside the external fluid volume, and contains all rotating parts but no fixed support.
5. The cylinder must become a fluid cell zone. It is not a rotating solid and must not be assigned as a wall.
6. Finish editing and choose **Update** in the simulation Geometry panel. SimScale requires manual acceptance of CAD edits. (source: https://www.simscale.com/docs/cad-preparation/cad-mode/)

## 5. Create Simulation Physics

1. Select the updated geometry and choose **Create simulation > Incompressible**. The reported velocities support an incompressible external-aerodynamics model. (source: sources/vj20.md, https://www.simscale.com/docs/analysis-types/incompressible-fluid-flow-analysis/)
2. In **Global settings**, set:
   - Time dependency: **Transient**
   - Turbulence model: **k-epsilon** for the source-matched baseline
   - Algorithm: retain SimScale's transient default initially
3. After baseline verification, copy the simulation and change only the turbulence model to **k-omega SST**. `vj20` uses k-epsilon while HRI uses and recommends SST for wall-bounded VAWT flow. Neither source proves one universal best model. (source: sources/vj20.md, sources/HRI2526.md)

## 6. Material And Initial Conditions

1. Assign air under **Materials** and keep density and viscosity identical in all sensitivity cases.
2. Set initial velocity to `(3.63, 0, 0) m/s` and initial gauge pressure to `0 Pa`.
3. Use one documented inlet turbulence intensity and length scale across all cases. `vj20` describes controlled tunnel flow but does not state its CFD turbulence inputs, so this remains an unverified validation input. (source: sources/vj20.md)
4. Leave potential-flow initialization off for the baseline. Enable it only as a documented stability intervention. (source: https://www.simscale.com/docs/simulation-setup/simulation-control-fluid/)

## 7. Boundary Conditions

1. Add **Velocity inlet** on the upstream `X min` face with velocity `(3.63, 0, 0) m/s` and the chosen turbulence inputs.
2. Add **Pressure outlet** on the downstream `X max` face with gauge pressure `0 Pa`.
3. Add **Symmetry** to both `Y` faces and both `Z` faces.
4. Add **Wall** with no-slip to all blade and shaft surfaces. Full resolution turbulence.
5. Inspect the boundary-condition visualization. In an incompressible analysis, an unassigned face defaults to a no-slip wall and invalidates this external-flow setup. (source: sources/vj20.md, https://www.simscale.com/docs/simulation-setup/boundary-conditions/)

## 8. Configure AMI

1. Under **Advanced concepts > Rotating zones**, create an **AMI** zone.
2. Set rotating motion, point on rotation axis `(0, 0, 0)`, rotation axis `(0, 0, 1)`, and rotational velocity `62.2 rad/s`.
3. Assign the cylinder cell zone created during meshing.
4. Use the right-hand rule. If rotation is reversed, use axis `(0, 0, -1)` instead of reversing the inflow.
5. AMI physically rotates the inner fluid mesh every timestep. MRF is a steady rotating-frame approximation and cannot provide this study's azimuthal torque history. (source: sources/HRI2526.md, sources/vj20.md, https://www.simscale.com/docs/simulation-setup/advanced-concepts/rotating-zones/)

## 9. Add Result Controls

1. Add **Forces and moments** on all blade and shaft walls.
2. Set center of rotation `(0, 0, 0)` and write interval `1` timestep.
3. Confirm the `Z`-axis moment sign represents power-producing shaft torque before calculating performance.
4. Optionally add separate moment controls for outer rotor, inner rotor, and shaft.
5. Enable field calculations for pressure coefficient, vorticity, wall shear stress, and turbulence fields.
6. Add upstream and downstream wake probes or probe lines.
7. SimScale's force and moment control integrates pressure and skin friction over assigned surfaces; it is the primary performance output. (source: https://www.simscale.com/docs/simulation-setup/result-control/forces-and-moments/)

## 10. Set Transient Controls

1. For the first AMI and mesh screening run, use an angular timestep of `0.50 degrees`:

```text
Delta t = Delta theta * pi / (180 * omega)
        = 0.50 * pi / (180 * 62.2)
        = 1.40e-4 s
```

2. Simulate `4` revolutions for this screening run:

```text
T_revolution = 2*pi / 62.2 = 0.101 s
End time = 4 * 0.101 = 0.404 s
```

3. This screening case has about `2,880` solver steps, about one tenth of the former `20`-revolution, `0.25 degree` setup. Set **Maximum runtime** only high enough for this screen's revised estimate; do not solve the runtime problem by simply allowing the original run to consume more time.
4. Choose **Write control = Time step** and **Write interval = 72** for about `40` field states. If the selected mode is **Runtime** or **Adjustable runtime**, use `0.01 s` instead. SimScale defines the interval units differently for these modes. (source: sources/ca18.md)
5. Keep the **Forces and moments** result-control interval at `1` timestep so the shaft-torque history remains time-resolved. Use the sparse field outputs only to inspect the overall solution and wake.
6. Treat this run as a setup and cost screen only. A `0.5 degree` step was sufficient only for moderate-to-high-TSR attached-flow cases in the available 2D evidence; separation may require a finer step. It is not enough to claim time-step independence or validated `Cp` for this 3D hybrid. (source: sources/va32.md)
7. If the screen completes cleanly, create a coarser mesh by changing only blade, AMI, and near-wake refinement; retain inflation, boundary conditions, domain, and physics. Compare its torque waveform and mean torque with the current mesh before committing to a longer run. Do not simultaneously coarsen the mesh and increase the timestep. (source: sources/vj20.md)
8. For a later accuracy check, rerun the selected mesh at `0.25 degrees` and `0.50 degrees` over a duration long enough to compare repeatable final cycles. Do not copy `vj20`'s `0.05 s` Fluent timestep. The available 2D evidence samples only after `20-30` revolutions, which is a target to reassess rather than copy directly to this 3D case. (source: sources/vj20.md, sources/va32.md)

## 11. Create Meshes

1. Select **Hex-dominant parametric** meshing.
2. Add a **surface refinement** to the closed AMI cylinder. Enable **With cell zone** and name it `AMI_rotor_zone`.
3. Create a separate **Surface refinement - rotor walls**. Clear its default face list, then assign only the same blade and shaft faces used by the no-slip wall condition and Forces and moments result control. Do not assign every non-external face: keep the AMI-cylinder interface and unrelated internal faces out of this refinement.
    - For the Run 4 recovery mesh, use **Min level = 3** and **Max level = 4** on the blade and shaft wall faces. This is a targeted increase from Run 2's levels `2-3`, which still defeatured `101` required faces.
    - Temporarily disable the custom feature refinement for this recovery mesh. Run 2 used feature levels `1` at `0.01 m` and `2` at `0.005 m`; those levels are coarser than the rotor-wall setting and can override it at blade edges.
   - If selecting many rotor sub-faces is impractical, create a topological entity set for all blade and shaft faces and reuse that set for the wall condition, result control, and rotor-wall surface refinement. (source: sources/ca1.md)
4. Keep the AMI-cylinder surface refinement separate and set it **With cell zone** named `AMI_rotor_zone`; it must not use the rotor-wall face list.
5. Feature refinement overrides surface refinement at geometry edges. For Run 4, leave the custom feature refinement disabled until the Event log confirms that every required blade and shaft face is retained. Only then re-enable it with every edge-level at least as fine as the rotor-wall setting (level `3` or finer at the relevant blade edges); do not use a `1 m` distance. Remesh and repeat the Event-log check after re-enabling it. (source: sources/ca21.md)
6. Add region refinement inside the AMI zone, then in a near-wake box (1.7) immediately downstream, then a coarser far-wake box (1.2).
7. Add boundary-layer inflation only to the blade and shaft wall face set used by the no-slip and Forces and moments controls. Do not assign all `147` internal flow-region faces: this includes the AMI interface and unrelated faces that must not receive inflation.
    - Layers: `15`
    - Growth ratio: `1.4`
    - First layer: calculate for the selected wall treatment, then verify using solved `y+`. The previous trial began at `1e-4 m`; do not use Run 4's `0.2 m` final-layer thickness because it is larger than the `0.0496 m` blade chord.
1. These layer settings match `vj20`. Target solved `y+ < 5` in the k-epsilon source-matched case and approximately `y+ = 1` in the SST sensitivity case. (source: sources/vj20.md, sources/HRI2526.md, sources/cj2.md)
2. Generate a coarse screening mesh before the medium and fine meshes. Change only blade, AMI, and near-wake sizes; keep all physics, timestep, and output controls fixed.
3. Select the first mesh whose cycle-mean torque and `Cp` change negligibly against the next finer mesh. `vj20`'s `321,189` nodes are not a transferable target. (source: sources/vj20.md)
4. Inspect mesh quality. Keep maximum non-orthogonality below `70`, improve above `80`, and do not accept above `85`. (source: https://www.simscale.com/docs/simulation-setup/meshing/mesh-quality/)
5. Open the mesh **Event log** before running. If it says that faces assigned to a no-slip boundary condition or Forces and moments control were defeatured and will be ignored, do not run. Click **select all** in the warning to identify the omitted faces. First verify that only required blade and shaft faces are assigned to the wall and result controls. For Run 4, use the rotor-wall surface levels `3-4` with custom feature refinement disabled, then remesh. Do not proceed until the warning lists zero required blade or shaft faces. If required faces still disappear, inspect the CAD for unnecessary tiny manufacturing faces or sharp details and repair/remove only details that are not part of the aerodynamic geometry. Do not rely on global fineness alone, because local refinement targets the geometry that must remain in the mesh. (source: sources/ca3.md, sources/ca21.md)

## 12. Post-process And Compare

1. Plot shaft moment versus time and convert to azimuth:

```text
theta_degrees = omega * time * 180 / pi
```

2. Do not average startup torque. Wait for a repeatable cycle, then average at least the final two full revolutions. The stronger 2D H-rotor evidence samples after `20-30` revolutions; the 3D case must independently demonstrate periodicity. (source: sources/vj20.md, sources/va32.md)
3. Calculate performance:

```text
P = T_mean * omega
A = D_outer * H_outer = 0.350 * 0.283 = 0.0991 m^2
Cp = P / (0.5 * rho * A * U_infinity^3)
```

4. HRI defines VAWT swept area as height times diameter. (source: sources/HRI2526.md)
5. Compare `Cp`, torque waveform, velocity deficit, pressure distribution, and wake observations with the `vj20` evidence.
6. After passing mesh, timestep, and periodicity checks, run a TSR sweep at `1, 2, 3, 4, 5`.

## Acceptance And Failure Checks

- **Zero-output diagnostic:** If `y+`, forces, and moments are all zero, do not interpret the run or continue refining it. First check the completed run's final simulated time and solver log: it must reach the configured `0.404 s`. Then inspect the mesh and boundary-condition visualization: the external-flow volume must be a material-assigned fluid body with blade and shaft cavities; the selected no-slip walls and Forces and moments surfaces must be those resulting fluid-volume faces; the velocity inlet must be on `X min`; and the AMI cylinder must be a fluid cell zone, not a wall. A zero result commonly indicates that the monitored walls or rotating zone are not in the solved fluid region. (source: sources/ca6.md, sources/ca14.md, sources/ca19.md, sources/cj8.md)
- **Defeatured-face gate:** Run 3 again reported `101` faces assigned to both result controls and boundary conditions as defeatured. This invalidates the load result and is a likely contributor to the early divergence. Do not reduce relaxation factors or change numerical schemes yet: first produce a mesh that retains every required blade and shaft face, inspect its quality near walls and sharp corners, and only then assess any remaining divergence. (source: SimScale Run 3 error message)
- **Quality gate:** Do not solve a mesh with maximum non-orthogonality above `85`. Run 4's `88.5` maximum and `93` cells above `88 degrees` must be located in the Mesh Quality viewer/Isovolume and corrected through CAD or mesh settings before a transient run. Non-orthogonal correctors are not a remedy above `85`; SimScale directs the user to improve the mesh instead. (source: sources/ca22.md, SimScale Run 4 warning)
- Treat the case as technically usable only after mesh and timestep changes no longer materially change mean torque or `Cp`.
- Use the `vj20` target as a reported comparison, not proof: `Cp` about `0.478` at the stated experimental condition and `0.486` in the paper's computational comparison. (source: sources/vj20.md)
- If `Cp` rises indefinitely as TSR rises, stop interpreting the sweep as validated. HRI reported this failure even with AMI and attributed it to unresolved parasitic-force prediction. (source: sources/HRI2526.md)
- Next check: complete a separate airfoil-level validation at a matching Reynolds number before relying on whole-rotor performance.



## Run History

### Run 1: FAIL
- Outcome: defeatured faces resulted in forces and moments not being captured.
- Mesh settings: not recorded in the available run notes.
### Run 2: FAIL
- Outcome: faces were still defeatured and `y+`, forces, and moments were all `0`.
- Mesh settings:
	- Feature refinement 6: included angle `150 degrees`; distance refinement `0.01 m` at level `1` and `0.005 m` at level `2`.
	- Surface refinement 2: min level `2`, max level `3`, without cell zone, with `147` assigned flow-region faces.
![[Pasted image 20260721140548.png|209]] ![[Pasted image 20260721140634.png|224]]

## Run 3: FAIL

- Outcome: `101` faces assigned to both the result controls and boundary conditions were defeatured; the solution diverged after `1%` progress.
![[Pasted image 20260723102150.png|184]]![[Pasted image 20260723102211.png|200]]![[Pasted image 20260723102319.png|198]]![[Pasted image 20260723102355.png|187]]![[Pasted image 20260723102420.png|218]]![[Pasted image 20260723102430.png|203]]![[Pasted image 20260723102442.png|208]]![[Pasted image 20260723102502.png|214]]

> [!Error]- Error Message
> |   |   |
|---|---|
|**Result controls** have been applied on the following topological entities: [face 2560@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2416@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2422@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2509@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2187@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2303@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 1990@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2299@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2584@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), and 91 more ([select all](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#)). These faces have been defeatured because the meshing parameters are too coarse and will be ignored. However, if they are pertinent to your simulation, please refine the mesh further or review your result control setup.|   |
|**Boundary conditions** have been applied on the following faces: [face 2560@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2416@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2422@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2509@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2187@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2303@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 1990@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2299@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), [face 2584@Flow region](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#), and 91 more ([select all](https://www.simscale.com/workbench/?pid=4544377268423106958&mi=run:49%2Csimulation:22&mt=SIMULATION_RUN#)). These faces have been defeatured because the meshing parameters are too coarse. The boundary conditions will be ignored because they have been assessed to be non-critical to the simulation setup. However, if they are pertinent to your simulation, please refine the mesh further or review your boundary condition setup.|   |
|Job was prepared successfully.|   |
|Run pre-processing finished.|   |
|The solution diverged, please check your simulation setup. Divergence can also be caused by bad elements in the mesh. Such elements tend to exist near walls and sharp corners. Visually inspect your mesh to locate them and re-mesh with additional refinements in their vicinity. If you are confident about the mesh-quality, please reduce relaxation factors and use more conservative numerical schemes.|   |

## Run 4: MESH REJECTED

- Outcome: the supplied note did not report a defeatured-face warning, but the Event log must still be checked for it. Maximum non-orthogonality was `88.5` with `93` cells above `88 degrees`. Do not run this mesh.
- Recorded settings before the Run 5 guidance update:
  - Rotating-zone refinement min/max levels `3/4`.
  - Rotor-wall surface refinement min/max levels `7/8`.
  - Wake-region refinement levels `3` and `4`.
  - Boundary-layer inflation assigned to `147` flow-region faces: `15` layers, expansion ratio `1.2`, minimum thickness `1e-5 m`, and final-layer thickness `0.2 m`.

![[Pasted image 20260723113343.png|220]]

> [!Warning]- Mesh Quality Warning
> |   |   |
|---|---|
|Max. Non-orthogonality:|88.5|
|Number of cells with Non-orthogonality > 88 deg:|93|
|Some mesh elements have quality metrics outside the recommended ranges. We suggest you refine the mesh before running a simulation. Please find more in-depth information in [our documentation.](https://www.simscale.com/docs/simulation-setup/meshing/mesh-quality)|   |

### Run 5: Mesh-Only Recovery

1. Keep Run 4's rotating-zone, rotor-wall, and wake refinements unchanged. This isolates the boundary-layer correction rather than increasing multiple refinements again.
2. Clear the `147`-face boundary-layer assignment. Create or reuse a blade-and-shaft-only topological face set, use it for the no-slip boundary condition, Forces and moments control, and inflation, and exclude AMI and all unrelated internal faces.
3. Use `15` layers and growth ratio `1.4`. Replace the `0.2 m` final-layer thickness with a wall-treatment-based first-layer thickness; start from the prior `1e-4 m` trial only if a calculated value is not yet available.
4. Generate the mesh but do not solve it. Use Mesh Quality/Isovolume to locate the cells above `88 degrees`; hide parts and use the view reset if they are too small to find. Inspect whether they occur at blade edges, the AMI interface, inflation transitions, or a CAD detail.
5. Release the mesh only when both gates pass: no required blade/shaft face is defeatured and maximum non-orthogonality is below `85` (target below `70`). Do not add non-orthogonal correctors or use more conservative schemes while the maximum remains above `85`. (source: sources/ca22.md)

# August 5 

### Mesh 49 progress
- **General Settings:**
    - Standard algorithm
    - Automatic sizing
    - Fineness of 5
    - Automatic curvature
    - Automatic boundary layers is turned off
    - Physics based meshing is turned on
    - Hex element core is off
    - Automatic extrusion meshing is off
    - 48 preferred number of CPUs and a max meshing run time of 1.8e+4
- **Advanced Settings:**
    - Automatic feature suppression of 1e-5
    - Gap refinement factor of 0.5
    - Global graduation rate of 1.22
- **Surface Custom Refinements:**
    - Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
        - _Default size:_ 0.001 m
        - _Min size:_ 0.00025 m
    - Shaft & Supporting Struts
        - _Default size:_ 0.0015 m
        - _Min size:_ 0.0004 m
    - Cylinder Surface Refinement
        - _Sizing mode:_ Automatic
        - _Fineness:_ 9.2
- **Volumetric Region Refinements:**
	- Cylinder: global automatic settings - fineness of 9 
    - Small Wake Box: global automatic sizing- fineness of 8.5
    - Large Wake Box: global automatic sizing- fineness of 8
- **Boundary Layer Inflation Refinements:**
    - Outer Blades, Inner Blades, Shaft + Struts, & Blade Tips (Trailing Edge Face)
        - _Number of layers:_ 7
        - _Overall relative thickness:_ 0.5
        - _Growth rate:_ 1.4


### Mesh 50 progress 
#### Settings overview:
- **General Settings:** 
	- standard algorithm 
		- automatic sizing
		- fineness of 5 
		- automatic curvature
	- automatic boundary layers is turned off
	- physics based meshing is turned off 
	- hex element core is off 
	- automatic extrusion meshing is off 
	- 48 preferred number of CPUs and a max meshing run time of 1.8e+4
	- **advanced settings:** 
		- automatic feature suppression of 1e-5
		- gap refinement factor of 0.5 
		- global graduation rate of 1.22
- **Surface Custom Refinements:**
	- Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
		- *Default size:* 0.0015 m 
		- *Min size*: 0.00035 m 
	- Shaft & Supporting Struts
		- *Default size:* 0.0015 m
		- *Min size:* 0.0004 m
- **Volumetric Region Refinements:**
	- Cylinder Box
		- *Default size:* 0.002 m
	-  Small Wake Box 
		- *Default size:* 0.003 m
	- Large Wake Box
		- *Default size:* 0.006 m
- **Boundary Layer Inflation Refinements:**
	- Outer Blades, Inner Blades, & Shaft + Struts
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3
		- *Growth rate*: 1.2
	- Blade Tips (Trailing Edge Face)
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3 
		- *Growth rate*: 1.2

### Mesh 50 progress 
#### Settings overview:
- **General Settings:** 
	- standard algorithm 
		- automatic sizing
		- fineness of 5 
		- automatic curvature
	- automatic boundary layers is turned off
	- physics based meshing is turned off 
	- hex element core is off 
	- automatic extrusion meshing is off 
	- 96 preferred number of CPUs and a max meshing run time of 1.8e+4
	- **advanced settings:** 
		- automatic feature suppression of 1e-5
		- gap refinement factor of 0.5 
		- global graduation rate of 1.22
- **Surface Custom Refinements:**
	- Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
		- *Default size:* 0.0015 m 
		- *Min size*: 0.00035 m 
	- Shaft & Supporting Struts
		- *Default size:* 0.0015 m
		- *Min size:* 0.0004 m
- **Volumetric Region Refinements:**
	- Cylinder Box
		- *Default size:* 0.002 m
- **Boundary Layer Inflation Refinements:**
	- Outer Blades, Inner Blades, & Shaft + Struts
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3
		- *Growth rate*: 1.2
	- Blade Tips (Trailing Edge Face)
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3 
		- *Growth rate*: 1.2
## mesh 61
Settings overview:
- **General Settings:** 
	- standard algorithm 
		- maual sizing
			- Maximum edge length 0.2
			- minimum edge length 0.075
	- automatic boundary layers is turned off
	- physics based meshing is turned off 
	- hex element core is off 
	- automatic extrusion meshing is off 
	- 96 preferred number of CPUs and a max meshing run time of 1.8e+4
	- **advanced settings:** 
		- automatic feature suppression of 1e-5
		- gap refinement factor of 0.5 
		- global graduation rate of 1.22
- **Surface Custom Refinements:**
	- Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
		- *Default size:* 0.0015 m 
		- *Min size*: 0.00035 m 
	- Shaft & Supporting Struts
		- *Default size:* 0.0015 m
		- *Min size:* 0.0004 m
- **Volumetric Region Refinements:**
	- Cylinder Box
		- sizing mode distance 
		- ![[Pasted image 20260812110335.png|220]]
	- close wake 
		- sizng mode distance 
			- ![[Pasted image 20260812110311.png|194]]
- **Boundary Layer Inflation Refinements:**
	- Outer Blades, & Shaft + Struts
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3
		- *Growth rate*: 1.2
	- Blade Tips (Trailing Edge Face)
		- *Number of layers:* 6
		- *Overall relative thickness*: 0.3 
		- *Growth rate*: 1.2
	- Inner Blades
		- *Number of layers:* 7
		- *Overall relative thickness*: 0.5
		- *Growth rate*: 1.2
## mesh 62 - an attempt to fix the boundary layers 
- **General Settings:** 
	- standard algorithm 
		- maual sizing
			- Maximum edge length 0.2
			- minimum edge length 0.075
	- automatic boundary layers is turned off
	- physics based meshing is turned off 
	- hex element core is off 
	- automatic extrusion meshing is off 
	- 96 preferred number of CPUs and a max meshing run time of 1.8e+4
	- **advanced settings:** 
		- automatic feature suppression of 1e-5
		- gap refinement factor of 0.5 
		- global graduation rate of 1.22
- **Surface Custom Refinements:**
	- Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
		- *Default size:* 0.0015 m 
		- *Min size*: 0.00035 m 
	- Shaft & Supporting Struts
		- *Default size:* 0.0015 m
		- *Min size:* 0.0004 m
- **Volumetric Region Refinements:**
	- Cylinder Box
		- sizing mode distance 
		- ![[Pasted image 20260812110335.png|220]]
	- close wake 
		- sizng mode distance 
			- ![[Pasted image 20260812110311.png|194]]
- **Boundary Layer Inflation Refinements:**
	- Outer Blades, Blade Tips, Inner Blades, & Shaft + Struts
		- *Number of layers:* 7
		- *Overall absolute thickness*: 0.002
		- *First layer thickness*: 0.0001
-the difference between this and the last is that i switched from relative boundary layers to absolute - no more growth rate 
- the non-orthogonality is down to 75!!!! 

## mesh 63: 
Settings overview:
- **General Settings:** 
	- standard algorithm 
		- maual sizing
			- Maximum edge length 0.2
			- minimum edge length 0.075
	- automatic boundary layers is turned off
	- physics based meshing is turned off 
	- hex element core is off 
	- automatic extrusion meshing is off 
	- 96 preferred number of CPUs and a max meshing run time of 1.8e+4
	- **advanced settings:** 
		- automatic feature suppression of 1e-5
		- gap refinement factor of 0.5 
		- global graduation rate of 1.22
- **Surface Custom Refinements:**
	- Outer Blades, Inner Blades, Blade Tips, & Trailing Edges
		- *Default size:* 0.0015 m 
		- *Min size*: 0.00035 m 
	- Shaft & Supporting Struts
		- *Default size:* 0.0015 m
		- *Min size:* 0.0004 m
- **Volumetric Region Refinements:**
	- Cylinder Box
		- sizing mode distance 
		- ![[Pasted image 20260812110335.png|220]]
	- close wake 
		- sizng mode distance 
			- ![[Pasted image 20260812110311.png|194]]
- **Boundary Layer Inflation Refinements:**
	- Outer Blades, Blade Tips, Inner Blades, & Shaft + Struts
		- *Number of layers:* 6
		- *Overall absolute thickness*: 0.0015
		- *First layer thickness*: 0.0001
-only change is to the boundary layers bc mesh 62 was looking too thick so i made the overall thickness smaller and reduced the number of layers 
