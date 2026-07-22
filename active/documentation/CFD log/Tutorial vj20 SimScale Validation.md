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
   - Start with **Min level = 2** and **Max level = 3**. These are a local screening increase because levels `1-2` defeatured required rotor faces; confirm against the Event log before running.
   - If selecting many rotor sub-faces is impractical, create a topological entity set for all blade and shaft faces and reuse that set for the wall condition, result control, and rotor-wall surface refinement. (source: sources/ca1.md)
4. Keep the AMI-cylinder surface refinement separate and set it **With cell zone** named `AMI_rotor_zone`; it must not use the rotor-wall face list.
5. Feature refinement overrides surface refinement at geometry edges. While diagnosing defeatured rotor walls, temporarily disable the custom feature refinement and remesh so the rotor-wall surface refinement can be tested in isolation. If the required faces are retained, re-enable feature refinement with every edge-level at least as fine as the rotor-wall surface refinement; do not use a `1 m` distance. (source: sources/ca21.md)
6. Add region refinement inside the AMI zone, then in a near-wake box (1.7) immediately downstream, then a coarser far-wake box (1.2).
7. Add boundary-layer inflation to blade and shaft walls:
   - Layers: `15`
   - Growth ratio: `1.4`
   - First layer: calculate for the selected wall treatment, then verify using solved `y+`. (started at 1e-4)
1. These layer settings match `vj20`. Target solved `y+ < 5` in the k-epsilon source-matched case and approximately `y+ = 1` in the SST sensitivity case. (source: sources/vj20.md, sources/HRI2526.md, sources/cj2.md)
2. Generate a coarse screening mesh before the medium and fine meshes. Change only blade, AMI, and near-wake sizes; keep all physics, timestep, and output controls fixed.
3. Select the first mesh whose cycle-mean torque and `Cp` change negligibly against the next finer mesh. `vj20`'s `321,189` nodes are not a transferable target. (source: sources/vj20.md)
4. Inspect mesh quality. Keep maximum non-orthogonality below `70`, improve above `80`, and do not accept above `85`. (source: https://www.simscale.com/docs/simulation-setup/meshing/mesh-quality/)
5. Open the mesh **Event log** before running. If it says that faces assigned to a no-slip boundary condition or Forces and moments control were defeatured and will be ignored, do not run. Click **select all** in the warning to identify the omitted faces. First verify that only required blade and shaft faces are assigned to the wall and result controls. Next, test the rotor-wall surface refinement with custom feature refinement disabled; then reintroduce feature refinement at equal-or-finer levels. If required faces still disappear, inspect the CAD for unnecessary tiny manufacturing faces or sharp details and repair/remove only details that are not part of the aerodynamic geometry. Do not rely on global fineness alone, because local refinement targets the geometry that must remain in the mesh. (source: sources/ca3.md, sources/ca21.md)

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
- Treat the case as technically usable only after mesh and timestep changes no longer materially change mean torque or `Cp`.
- Use the `vj20` target as a reported comparison, not proof: `Cp` about `0.478` at the stated experimental condition and `0.486` in the paper's computational comparison. (source: sources/vj20.md)
- If `Cp` rises indefinitely as TSR rises, stop interpreting the sweep as validated. HRI reported this failure even with AMI and attributed it to unresolved parasitic-force prediction. (source: sources/HRI2526.md)
- Next check: complete a separate airfoil-level validation at a matching Reynolds number before relying on whole-rotor performance.



## Run 1: FAIL
defeatured faces resulted in forces and moments not being captured

## Run 2:
adjusted mesh settings with LLM guidance as follows:

![[Pasted image 20260721140548.png|209]] ![[Pasted image 20260721140634.png|224]]
