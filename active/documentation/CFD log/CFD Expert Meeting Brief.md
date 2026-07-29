# CFD Expert Meeting Brief: NACA 0018 Validation and VJ20 Setup

## Meeting Goal

1. Establish a defensible, limited validation workflow for the NACA 0018 airfoil before using the workflow to compare VAWT designs.
2. Review the initial SimScale setup for the scaled VJ20 hybrid VAWT and identify the smallest credible first turbine-validation run.

## Materials To Have Open

- [[active/documentation/CFD log/Airfoil Validation Studies]]: run-by-run inputs, mesh images, and results.
- [[active/documentation/Airfoil Validation Study Summary and Report Outline]]: prior synthesis of the airfoil work.
- [[active/documentation/CFD log/Tutorial vj20 SimScale Validation|VJ20 SimScale validation tutorial]]: proposed VJ20 workflow and source-specific targets.
- [[active/resources/CFD, SimScale Notes]]: setup notes and checklist.
- [[sources/cj9]]: low-Reynolds-number NACA 0018 experimental and CFD context.
- [[sources/vj20]]: VJ20 geometry, test condition, and CFD method.

## Part 1: NACA 0018 Airfoil Validation

### Purpose

We are trying to validate an airfoil-level CFD workflow before interpreting whole-turbine `Cp` or torque results. This is an incomplete validation effort, not evidence that the final VAWT model is already validated. (source: active/documentation/Airfoil Validation Study Summary and Report Outline.md)

### Current Comparison Case

| Item                       | Current recorded value                                                                                                                                                                  |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Airfoil                    | NACA 0018, rounded trailing edge in the later cases                                                                                                                                     |
| Angle of attack            | `5 deg`                                                                                                                                                                                 |
| Nominal Reynolds number    | `50,000`                                                                                                                                                                                |
| Chord                      | `1.0 m`                                                                                                                                                                                 |
| Inlet velocity             | `0.7645 m/s`                                                                                                                                                                            |
| Solver                     | incompressible, steady-state, `k-omega SST`                                                                                                                                             |
| Domain used in later cases | `x = -10` to `15 m`; `y = -8` to `8 m`; `z = -0.25` to `0.25 m`                                                                                                                         |
| Outer boundaries           | velocity inlet, `0 Pa` pressure outlet, slip outer walls                                                                                                                                |
| Airfoil wall               | no-slip; the run log labels the final rounded-tail case as a wall-function case, but the user reports full resolution in SimScale. Verify the saved case before using this as evidence. |
| Force coefficients         | lift `+y`, drag `+x`, `U = 0.7645 m/s`, `L = 1 m`, `A = 0.5 m2`                                                                                                                         |

(source: active/documentation/CFD log/Airfoil Validation Studies.md)

### What We Tried

- Tested default and boundary-layer-inflated meshes, Hex Automatic meshing, medium-to-high fineness, first-layer sizes, small-feature suppression, one versus two non-orthogonal correctors, wall function versus full-resolution walls, automatic versus `0.001` turbulence intensity, and enlarged versus reduced-span domains. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- Re-drew the airfoil CAD, inspected STEP scale/orientation/thickness, and changed to a `0.5 m` spanwise domain to approximate a two-dimensional comparison. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- Corrected the reference area from `1.0 m2` to `0.5 m2` after reducing the wetted span to `0.5 m`. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- Rounded the trailing edge after sharp-tail boundary-layer meshes produced high non-orthogonality near the trailing edge. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- Ran NACA 0012, NACA 0010, and NACA 0015 controls using the later setup. The NACA 0010 and NACA 0015 runs had high non-orthogonality, so they are not clean controls. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- Tried a `Re = 500,000` NACA 0018 case; it did not materially resolve the low-lift result. The first velocity calculation for that run was incorrect and was manually corrected before rerunning. (source: active/_Julie_daily_log.md)

### Best-Documented Current Result

The later rounded-tail pseudo-2D NACA 0018 case used first-layer size `0.00001 m`, small-feature suppression `0.000001 m`, and two non-orthogonal correctors. It recorded maximum `y+ = 4.913`, `Cl = 0.570`, and `Cd = 0.028`. Increasing fineness to `7` produced `Cl = 0.572`, `Cd = 0.030`, so this limited change did not materially alter the result. (source: active/documentation/CFD log/Airfoil Validation Studies.md)

### Why We Are Stuck

- The early AirfoilTools comparison was approximately `Cl = 0.75` at the selected condition, while the best recorded NACA 0018 CFD lift is approximately `0.57`. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- The available NACA 0018 evidence is not a clean one-to-one benchmark: the project source reports low-Reynolds-number behavior that varies with Reynolds number and transition conditions, and reports that 2D Transition SST CFD underpredicted lift at `Re = 160,000`. (source: sources/cj9.md)
- The current NACA 0018 geometry has a rounded trailing edge, whereas the desired comparison is normally understood as an ideal NACA 0018. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- The record does not include a controlled mesh-independence, domain-independence, residual/convergence, or transition-model study. Several settings changed together in the exploratory work. (source: active/documentation/Airfoil Validation Study Summary and Report Outline.md)

### Useful Controls

- NACA 0012 under the rounded-tail setup recorded `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`, close to the team’s AirfoilTools-based target. This supports some shared setup elements but does not validate NACA 0018. (source: active/documentation/CFD log/Airfoil Validation Studies.md)
- NACA 0010 and NACA 0015 had maximum non-orthogonality around `87` and `89`, respectively. Their apparent trend with airfoil thickness should not be treated as established until mesh quality is improved. (source: active/documentation/CFD log/Airfoil Validation Studies.md)

### Questions For The Expert

1. Is our current `Re = 50,000`, `5 deg`, rounded-tail, pseudo-2D case comparable to any suitable published NACA 0018 data? If not, which exact benchmark condition should we use?
2. Does the `0.5 m` spanwise volume with slip walls represent a valid pseudo-2D setup in SimScale for this purpose, or should we use a different spanwise treatment and boundary condition?
3. Is the rounded trailing edge an acceptable mesh repair for this validation, or should we remake the geometry and mesh around a sharp trailing edge?
4. Is `k-omega SST` with the verified wall treatment appropriate at this Reynolds number? Should we run Transition SST, and what transition inputs should be specified?
5. What should the wall treatment and solved `y+` target be for the selected model? Are the current `y+` values and prism layers defensible?
6. What is the minimum controlled verification sequence: mesh levels, domain sizes, convergence evidence, and control airfoils?
7. Before changing settings further, what specific diagnostic should decide whether the remaining lift difference is from geometry, mesh, transition, reference data, or coefficient setup?

## Part 2: VJ20 Hybrid VAWT CFD Setup

### Goal

After the airfoil workflow is sufficiently validated, reproduce a clearly scoped VJ20 scaled-model operating point in SimScale and compare torque, `Cp`, and flow behavior with the paper without claiming exact reproduction of its Fluent model. (source: active/documentation/CFD log/Tutorial vj20 SimScale Validation.md; source: sources/vj20.md)

### VJ20 Reference Case

| Item | Value |
| --- | --- |
| Outer rotor | three NACA 0018 blades; `D = 0.350 m`, `H = 0.283 m`, chord `0.0496 m`, pitch `-2.82 deg` |
| Inner rotor | three DU 06-W-200 blades; `D = 0.143 m`, `H = 0.146 m`, chord `0.0497 m`, pitch `-3.41 deg` |
| Operating point | `U = 3.63 m/s`, `TSR = 3` |
| Source comparison values | experimental `Cp = 0.478`; reported computational `Cp = 0.486` |
| Angular velocity calculated from TSR | `62.2 rad/s` using the scaled outer radius `0.175 m` |

(source: active/documentation/CFD log/Tutorial vj20 SimScale Validation.md; source: sources/vj20.md)

### Current Setup Direction

- The intended screening model is 3D, transient, incompressible flow with an AMI rotating zone, a `1.5D` rotating cylinder, force and moment controls, and a `0.50 deg` angular time step; a later `0.25 deg` run is planned as a sensitivity check. (source: active/documentation/CFD log/Tutorial vj20 SimScale Validation.md)
- The VJ20 paper used Fluent, a sliding mesh, `k-epsilon`, a hybrid mesh with `15` inflation layers, and a reported `0.05 s` timestep. Its settings cannot be copied directly to SimScale without verification. (source: sources/vj20.md)
- The team generated a VJ20 mesh with maximum non-orthogonality of `70`, but the first two transient runs completed in about three minutes with no captured forces or moments. A third run did not complete after mesh changes. (source: active/_anna daily log.md)
- The daily record also notes a turbine run with zero reported forces, possibly related to the mesh. This has not been resolved. (source: active/_Julie_daily_log.md)

### VJ20 Questions For The Expert

1. Is AMI the right initial approach for this validation, or should we first use a simpler steady MRF or reduced model only to verify geometry, boundaries, and result controls?
2. Why would a transient run finish quickly while returning no force or moment output? Please inspect our selected faces, result-control write settings, timestep/end time, mesh/cell-zone assignment, and AMI configuration.
3. Is `62.2 rad/s` the correct rotational speed for the scaled geometry, `U = 3.63 m/s`, and `TSR = 3`? The paper’s scaled-speed table lists `37.06 rad/s`, which does not give TSR `3` with the listed diameter and wind speed. (source: active/documentation/CFD log/Tutorial vj20 SimScale Validation.md; source: sources/vj20.md)
4. What is the smallest credible staged run before attempting a full `20`-revolution, mesh-and-timestep-sensitive performance calculation?
5. Which outputs must be demonstrated before we interpret `Cp`: torque periodicity, force/moment signs and surfaces, residual behavior, solved `y+`, mesh quality, mesh sensitivity, timestep sensitivity, and wake/domain checks?
6. Should the first source-matched comparison use `k-epsilon`, or should `k-omega SST` be the baseline in SimScale? What is the justification and wall-resolution requirement for that choice?

## Meeting Outcome To Capture

Before leaving the meeting, write down:

- The exact NACA 0018 benchmark paper, Reynolds number, angle of attack, geometry, transition/turbulence conditions, and target `Cl`/`Cd`.
- The one-variable-at-a-time rerun sequence and acceptance criterion for the airfoil case.
- The approved VJ20 baseline: geometry scale, flow domain, rotating-zone method, turbulence model, mesh/wall target, timestep, end time, and result controls.
- The first evidence required before using a VJ20 `Cp` result in a design decision.

## Known Limits

- The airfoil case is not yet validated; the current coefficients are model outputs, not confirmed physical values. (source: active/documentation/Airfoil Validation Study Summary and Report Outline.md)
- The VJ20 source contains internal scaling inconsistencies, including its tabulated scaled rotational speed versus its stated TSR condition. (source: sources/vj20.md)
- AI-generated recommendations were used as starting points, but at least one quantitative extraction in the project was incorrect. All numerical settings and source values should be checked directly in the underlying paper or SimScale project. (source: active/_Julie_daily_log.md)
