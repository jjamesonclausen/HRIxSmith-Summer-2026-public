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

1. Start with an angular timestep of `0.25 degrees`:

```text
Delta t = Delta theta * pi / (180 * omega)
        = 0.25 * pi / (180 * 62.2)
        = 7.02e-5 s
```

2. Simulate an initial `20` revolutions:

```text
T_revolution = 2*pi / 62.2 = 0.101 s
End time = 20 * 0.101 = 2.02 s
```

3. Write field data every `20` timesteps (`5 degrees`) and retain force/moment output every timestep.
4. Repeat the selected mesh at `0.10 degrees` and `0.50 degrees`. Compare final-period mean shaft torque and `Cp`; do not copy `vj20`'s `0.05 s` time step, which was specific to its Fluent case and passed its own sensitivity test. (source: sources/vj20.md, sources/va32.md)

## 11. Create Meshes

1. Select **Hex-dominant parametric** meshing.
2. Add a **surface refinement** to the closed AMI cylinder. Enable **With cell zone** and name it `AMI_rotor_zone`.
3. Add surface refinement to blades and shaft, and feature refinement to blade leading and trailing edges.
4. Add region refinement inside the AMI zone, then in a near-wake box immediately downstream, then a coarser far-wake box.
5. Add boundary-layer inflation to blade and shaft walls:
   - Layers: `15`
   - Growth ratio: `1.4`
   - First layer: calculate for the selected wall treatment, then verify using solved `y+`.
6. These layer settings match `vj20`. Target solved `y+ < 5` in the k-epsilon source-matched case and approximately `y+ = 1` in the SST sensitivity case. (source: sources/vj20.md, sources/HRI2526.md, sources/cj2.md)
7. Generate coarse, medium, and fine meshes. Change only blade, AMI, and near-wake sizes; keep all physics, timestep, and output controls fixed.
8. Select the first mesh whose cycle-mean torque and `Cp` change negligibly against the next finer mesh. `vj20`'s `321,189` nodes are not a transferable target. (source: sources/vj20.md)
9. Inspect mesh quality. Keep maximum non-orthogonality below `70`, improve above `80`, and do not accept above `85`. (source: https://www.simscale.com/docs/simulation-setup/meshing/mesh-quality/)

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

- Treat the case as technically usable only after mesh and timestep changes no longer materially change mean torque or `Cp`.
- Use the `vj20` target as a reported comparison, not proof: `Cp` about `0.478` at the stated experimental condition and `0.486` in the paper's computational comparison. (source: sources/vj20.md)
- If `Cp` rises indefinitely as TSR rises, stop interpreting the sweep as validated. HRI reported this failure even with AMI and attributed it to unresolved parasitic-force prediction. (source: sources/HRI2526.md)
- Next check: complete a separate airfoil-level validation at a matching Reynolds number before relying on whole-rotor performance.
