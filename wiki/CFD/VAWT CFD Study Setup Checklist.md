---
Created: 2026-07-20
Updated: 2026-07-20
Sources:
  - "[[ca3]]"
  - "[[ca4]]"
  - "[[ca6]]"
  - "[[ca14]]"
  - "[[ca15]]"
  - "[[ca19]]"
  - "[[ca21]]"
  - "[[ca22]]"
  - "[[cj8]]"
  - "[[HRI2526]]"
  - "[[va32]]"
  - "[[va33]]"
  - "[[vj20]]"
Source_count: 13
tags:
  - cfd
---
# VAWT CFD Study Setup Checklist

Use this checklist to construct a VAWT CFD study methodically. It combines SimScale workflow documentation with two validated 2D H-rotor URANS studies and one 3D hybrid-VAWT sliding-mesh study. Do not treat their numerical values as a universal recipe. (source: sources/ca4.md, sources/va32.md, sources/va33.md, sources/vj20.md)

## 1. Define one comparison target

1. State the turbine geometry, intended wind speed, prescribed rotational speed or TSR, and the output that will decide success: for example `Cp(TSR)`, mean shaft torque, dynamic torque coefficient, or static torque coefficient versus azimuth. (source: sources/ca19.md, sources/vj20.md)
2. Select a source-matched reference before building the model. Record the exact rotor geometry, air properties, inflow turbulence, rotational condition, and averaging interval alongside its target output. > Inference: CFD comparison is only interpretable when those influential inputs and the target output are held consistent. (source: sources/va32.md, sources/va33.md, sources/vj20.md)
3. For a first validation run, use a prescribed rotor speed. The documented VAWT studies set the rotation rather than solving the coupled generator/load response. (source: sources/va32.md, sources/va33.md, sources/vj20.md)

## 2. Prepare the rotor CAD

1. Model the flow-relevant rotor solids: blades, exposed shaft, and any supports whose aerodynamic drag is part of the target study. Remove tiny manufacturing details that do not affect the target flow and can damage meshing. (source: sources/ca3.md, sources/va33.md)
2. Check units, intersections, and overlaps. Resolve them before creating the flow volume; overlapping solids can cause geometry and meshing failures. (source: sources/ca3.md, sources/ca4.md)
3. Create an external fluid volume around the turbine, then subtract the rotor solids so the CFD domain is air, not solid turbine material. (source: sources/ca4.md)

## 3. Construct the rotating zone

1. In CAD, create a closed cylinder that encloses the rotor. Specify its rotation center, axis, radius, and height; for a face-derived cylinder, SimScale documents a `1.1` clearance factor for rotating machinery. (source: sources/ca4.md)
2. Keep the cylinder coaxial with the physical shaft. It must enclose every rotating solid and exclude stationary supports that are not intended to rotate. > Inference: every enclosed cell receives the rotating-zone property. (source: sources/ca4.md, sources/ca21.md)
3. Confirm that the cylinder overlaps a material-assigned fluid volume. A visually correct cylinder is not a usable zone unless it becomes a valid 3D fluid cell zone. (source: sources/cj8.md)
4. Manually update the simulation geometry after CAD edits. SimScale does not automatically replace an assigned simulation geometry with its edited version. (source: sources/ca4.md)

## 4. Convert the cylinder into rotating physics

1. For hex-dominant meshing, add a surface refinement to the **closed cylinder volume** and enable **Create cell zone**. This groups the enclosed fluid cells. (source: sources/ca21.md)
2. Confirm the cell zone exists after meshing. Cell zones are the required mesh object for MRF or AMI rotating-region assignment. (source: sources/ca21.md)
3. Choose the rotation representation deliberately. SimScale documents MRF and AMI rotating zones; a documented VAWT study describes MRF as a steady rotating-reference-frame approximation and AMI as transiently rotating the inner fluid domain. (source: sources/ca15.md, sources/HRI2526.md)
4. For a time-resolved torque or azimuthal-load validation, use a transient sliding/AMI-style moving interface if your solver supports it. This is an inference from the transient sliding-mesh setup used in the `vj20` torque study, not a general SimScale selection rule. (source: sources/vj20.md)
5. Enter the prescribed angular velocity with a documented axis and sign convention. Before solving, verify that a positive rotation moves the blade in the intended direction. (source: sources/ca4.md, sources/vj20.md)

## 5. Set the external-flow physics

1. Assign air material, a velocity inlet, pressure outlet, and appropriate lateral/top/bottom boundaries; confirm every face assignment in the boundary-condition visualization. (source: sources/ca6.md, sources/ca14.md)
2. Assign no-slip walls to every modeled rotor surface. The `vj20` sliding-mesh study applies wall conditions to blades and the central rotating shaft. (source: sources/vj20.md)
3. Specify inlet turbulence consistently with the validation reference. In the `va33` reference case, `5%` inlet turbulence decays to an incident value of `4.42%`, illustrating why inlet and rotor-incident turbulence must not be conflated. (source: sources/va33.md)
4. For a first 3D rotor study, do not claim a turbulence-model choice is validated merely because it converges. The captured sources use different models: transition SST in `va32`/`va33` and `k-epsilon` in `vj20`. (source: sources/va32.md, sources/va33.md, sources/vj20.md)

## 6. Mesh the flow features that drive the result

1. Use region and surface refinements around flow-sensitive rotor features, such as blade surfaces, the shaft, the rotating-zone boundary, and the near wake. > Inference: SimScale provides the refinement controls, while the named VAWT regions follow from the rotor-flow objective rather than a prescribed SimScale list. (source: sources/ca21.md)
2. Add boundary-layer inflation to the modeled rotor walls. Set layer count, expansion ratio, minimum thickness, and first-layer thickness; then check the solved `y+` field. (source: sources/ca21.md)
3. Inspect mesh quality before solving. SimScale recommends non-orthogonality below `70`, calls for mesh improvement above `80`, and warns that maximum values above `85` likely diverge. (source: sources/ca22.md)
4. Keep the whole mesh study controlled: change mesh density while holding geometry, motion, boundary conditions, and output calculations unchanged. > Inference: otherwise a result difference cannot be attributed to the mesh. (source: sources/ca22.md, sources/va32.md)

## 7. Select time resolution and run length

1. Express the transient step as an angular increment per time step and test it for the chosen rotor condition. The 2D NACA0018 study found `0.1 degrees` necessary in low-to-moderate-TSR or uncertain separation cases, while `0.5 degrees` was sufficient only for its attached-flow higher-TSR cases. (source: sources/va32.md)
2. As a starting check, the same 2D studies sample only after `20-30` revolutions have reached statistical steadiness. A full 3D rotor must demonstrate this separately from its own torque history. (source: sources/va32.md, sources/va33.md)
3. The `vj20` 3D hybrid case selected `0.05 s` at `TSR = 3` only after testing `1` to `0.005 s`; do the corresponding time-step study rather than copying its value. (source: sources/vj20.md)

## 8. Define outputs before running

1. Add force and moment result controls on the intended rotating solids. Record the axis, origin, and sign convention; these choices determine whether the reported moment represents turbine shaft torque. (source: sources/ca19.md)
2. Record instantaneous torque/moment every step or angular increment, then calculate a cycle average only after the signal becomes repeatable. The `vj20` case records moment at every time step and identifies quasi-steady behavior after about `1.9 s`. (source: sources/vj20.md)
3. If comparing torque coefficients, confirm the paper's definition. In `vj20`, `Ct` is dynamic torque coefficient and `Cts` is static torque coefficient, not thrust coefficient. (source: sources/vj20.md)
4. Save `Cp(TSR)`, torque coefficient, and, if applicable, static torque coefficient versus azimuth. Add velocity and pressure planes to inspect the wake and blade loading, but do not use attractive contours as convergence proof. (source: sources/ca19.md, sources/vj20.md)

## 9. Validate in this order

1. Match the published geometry and conditions.
2. Demonstrate mesh and time-step sensitivity for the chosen output.
3. Demonstrate repeatability across revolutions.
4. Compare the same coefficient definition and reference area with the source curve.
5. Only then add or change a design variable.

> Uncertainty: no captured source supplies a universal three-dimensional H-VAWT setup, including a general rotating-zone diameter, domain extent, turbulence model, time step, mesh count, or convergence threshold. Treat these steps as a defensible workflow, then validate the actual case against a source-matched benchmark. (source: sources/ca4.md, sources/ca21.md, sources/va32.md, sources/vj20.md)

Related pages: [[SimScale VAWT Rotating Region]], [[SimScale VAWT Domain and Boundaries]], [[SimScale VAWT Mesh and Quality]], [[SimScale VAWT Transient Runs and Outputs]], [[va32 VAWT URANS Computational Guidelines]], [[vj20 Proposed Hybrid VAWT]].
