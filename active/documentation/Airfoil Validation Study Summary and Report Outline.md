`Prompt:` Read through Airfoil Validation Studies.md and write a similar outline \[to [[Weeks 1-4 Project Summary and Report Outline]]\] that includes the most important tests done, what parameters were changed, what was learned, and where we left off. Remember that the process is not complete.

**Source:** [[active/documentation/CFD log/Airfoil Validation Studies]]

# Airfoil Validation Study Summary and Report Outline

## Scope and Status

This note summarizes the ongoing NACA0018 airfoil CFD comparison at `Re = 50,000` and `5 degrees` angle of attack. Its purpose is to establish a defensible airfoil workflow before using CFD for VAWT design comparisons. It is not a completed validation or a generally validated SimScale recipe.

## Starting Case and Reference Question

- The documented case uses a nominal NACA0018 with `1.0 m` chord, inlet velocity `0.7645 m/s`, air density `1.196 kg/m3`, and the stated Reynolds number and angle of attack.
- The initial comparison target was the AirfoilTools NACA0018 curve, later recorded as approximately `Cl = 0.75` at the study condition. A low-turbulence NACA0018 experiment in `cj9` reports different low-Re behavior, including `Clmax = 0.435` at `Re = 50,000` and `3 degrees`; the AirfoilTools curve is therefore not the only relevant reference.
- The later common setup was incompressible, steady-state `k-omega SST` with a velocity inlet, pressure outlet, slip outer boundaries, no-slip airfoil walls, and force coefficients using lift along `+y` and drag along `+x`.

## Important Test Sequence

### 1. Batch 1: exploratory mesh and domain tests

- Runs 1-5 tested default meshing, boundary-layer inflation, Hex Automatic meshing, medium fineness, a reduced spanwise domain, and a community-study-inspired setup. Outer-domain dimensions changed from `10 m` in every direction to `3 m` in every direction.
- Recorded NACA0018 results ranged from `Cl = 0.1306` to `0.261` and `Cd = 0.0397` to `0.061`. The first attempted 2D run had no usable result because result controls were not configured.
- **Lesson:** the early cases severely underpredicted lift and were not an adequate validation basis. They motivated a new project with explicit coefficient controls and a more systematic setup.

### 2. Batch 2: finite-span versus pseudo-2D and reference-area correction

- The new NACA0018 CAD with a finite-span outer volume of `x = -3` to `8 m`, `y = -4` to `4 m`, and `z = -4` to `4 m` gave `Cl = 0.177`, `Cd = 0.060`. Increasing the domain to `x = -10` to `15 m`, `y = -8` to `8 m`, and `z = -8` to `8 m` was recorded as essentially unchanged.
- Reducing the spanwise external-flow volume to `z = -0.25` to `0.25 m` improved the recorded result to `Cl = 0.291`, `Cd = 0.026`, but the result still used the former `1 m2` reference area and was flagged as inconsistent.
- Correcting the reference area to `A = 0.5 m2` for the `0.5 m` wetted span produced `Cl = 0.583`, `Cd = 0.052`. A later STEP-file review confirmed that the `0.5 m2` area is correct for the portion of airfoil retained in the subtracted external-flow volume.
- **Lesson:** a finite-span simulation is not directly comparable with a 2D airfoil reference. Reducing the spanwise domain and correcting coefficient normalization materially improved lift, but did not resolve the NACA0018 discrepancy.

### 3. Mesh-quality, `y+`, turbulence, and numerical tests

- Adding `y+` monitoring to the corrected pseudo-2D case recorded maximum `y+ = 18.61`. Specifying a `0.005 m` first-layer thickness did not improve the coefficients.
- Increasing mesh fineness to `8` changed the result to `Cl = 0.515`, `Cd = 0.041`: lower lift but improved drag.
- Changing inlet turbulence from automatic to intensity `0.001` produced no material improvement after the mesh settings were restored; the stabilized case recorded `Cl = 0.570`, `Cd = 0.051`, and maximum `y+ = 20.11`.
- Smaller first-layer sizes, full-resolution wall treatment, and boundary-layer settings were attempted. The sharp trailing edge generated high non-orthogonality errors during attempts to improve the near-wall mesh.
- Rounding the trailing edge, setting first-layer size to `0.00001 m`, small-feature suppression to `0.000001 m`, and using two non-orthogonal correctors gave maximum `y+ = 4.913`, `Cl = 0.570`, and `Cd = 0.028`. Increasing fineness to `7` left the result effectively unchanged at `Cl = 0.572`, `Cd = 0.030`.
- **Lesson:** the mesh changes improved drag and near-wall resolution, but did not remove the lift discrepancy. The log also identifies a setup pitfall: an inflate-boundary-layer refinement can overwrite automatic boundary-layer settings.

### 4. Controls and CAD checks

- NACA0012 Run 15 used the rounded-tail Run 13 settings and produced `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`. The study record describes this as closely matching the AirfoilTools-based NACA0012 target.
- A direct STEP comparison confirmed nominal `1 m` chord, nominal `12%` and `18%` thicknesses, equivalent rounded-tail topology, and opposite leading-edge directions that were corrected in SimScale.
- Supplementary NACA0010 and NACA0015 controls recorded high non-orthogonality. NACA0010 was logged as `Cl = 0.61`, `Cd = 0.27`; NACA0015 as `Cl = 0.58` versus an expected value near `0.68`, `Cd = 0.029`.
- **Lesson:** the NACA0012 control and CAD review found no shared domain, reference-area, scale, orientation, or rounded-tail-CAD issue explaining the NACA0018 lift gap. The NACA0010/0015 controls are preliminary because their mesh-quality issues remain unresolved.

## Parameters Changed

| Parameter | Changes | What was learned |
|---|---|---|
| Airfoil geometry | NACA0018; NACA0012, NACA0010, and NACA0015 controls; sharp and rounded trailing edges | Rounding made a lower-`y+` mesh feasible. The NACA0018 discrepancy persisted, while the NACA0012 control matched its target closely. |
| Domain and dimensionality | Large finite-span volumes; expanded streamwise/cross-stream dimensions; `0.5 m` pseudo-2D span | Enlarging the finite-span volume did not change the early result; reducing span and correcting area substantially increased reported lift. |
| Coefficient reference area | `1 m2` then `0.5 m2` | `0.5 m2` is consistent with the `0.5 m` wetted span of the pseudo-2D fluid volume. |
| Mesh and boundary layer | Default, inflation, Hex Automatic, fineness, first-layer size, feature suppression, wall function/full resolution | Improved `y+` and drag but did not resolve lift; automatic boundary-layer settings can be overridden by inflation refinement. |
| Turbulence input | Automatic versus intensity `0.001`; `k-omega SST` retained | The recorded low-intensity change did not materially alter the stabilized NACA0018 result. |
| Numerics | One versus two non-orthogonal correctors | Two correctors were present in the low-`y+` rounded-tail case, but their independent effect was not isolated. |

## Where We Left Off

- The best-documented NACA0018 cases predict approximately `Cl = 0.57`, below the AirfoilTools comparison of approximately `Cl = 0.75`, with drag improved to approximately `Cd = 0.028-0.030`.
- The NACA0012 control supports the shared workflow but does not validate NACA0018 or determine that the AirfoilTools reference is wrong. The rounded trailing edge also prevents a strict comparison with an ideal sharp NACA0018.
- The log advises against continuing to alter general settings simply to force the NACA0018 result toward one reference curve. The current result should be reported as the prediction of this steady, `k-omega SST`, rounded-NACA0018 pseudo-2D case.
- The next defensible step is a condition-matched low-Re benchmark with documented geometry, trailing-edge treatment, transition/turbulence conditions, dimensionality, mesh, convergence evidence, and measured coefficients. Only then should the workflow guide VAWT comparisons.

## Narrative Report Outline

### 1. Purpose: validate before designing

- State the airfoil comparison question and why it must precede VAWT design screening.
- Define the case and distinguish a validation attempt from a completed turbine-performance simulation.

### 2. Early exploration revealed the comparison problem

- Summarize Batch 1 and its low-lift results.
- Explain why finite-span modeling and a 2D reference could not be compared directly.

### 3. Create a consistent pseudo-2D case

- Describe the new CAD, explicit coefficient controls, pseudo-2D span, and corrected reference area.
- Present the lift improvement while retaining the unresolved reference gap.

### 4. Improve mesh quality without tuning to a target

- Present `y+`, mesh-fineness, turbulence-intensity, wall-treatment, trailing-edge, and non-orthogonality tests.
- Show that lower `y+` and better drag did not change the NACA0018 lift result.

### 5. Use controls to bound the conclusion

- Present NACA0012 as a successful shared-workflow control and the STEP review as a geometry/orientation check.
- Treat NACA0010 and NACA0015 as incomplete supplemental checks because of high non-orthogonality.
- Compare the AirfoilTools and `cj9` reference contexts without assuming either alone resolves the discrepancy.

### 6. Current result and next validation decision

- Report the NACA0018 output as model-specific, not as a proven physical coefficient.
- Identify the benchmark and verification evidence still needed before VAWT use.

## Uncertainty To Preserve

- The record does not include complete mesh-independence, domain-independence, convergence, or transition-model studies.
- The rounded NACA0018 is not an ideal sharp NACA0018, and the AirfoilTools and `cj9` references differ.
- The recorded NACA0010 drag value of `0.27` conflicts with its description as correct and should be checked against the SimScale result before it is reported.
