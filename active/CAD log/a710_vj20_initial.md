---
Created: 2026-07-10
Updated: 2026-07-10
Sources:
  - "[[vj20]]"
tags:
  - active
  - cad
---


This note has my llm wiki and zookeeper work for recreating the  `vj20` proposed hybrid VAWT as a dual-H-type turbine. *\*more a learning experiment* 

--- 
**From LLM:**
## Geometry

- The proposed turbine is a hybrid VAWT with an outer straight-bladed H-rotor and an inner asymmetric-airfoil H-rotor replacing the usual Savonius starter. (source: sources/vj20.md)
- The outer rotor uses three `NACA0018` blades. (source: sources/vj20.md)
- The inner rotor uses three `DU 06-W-200` blades. (source: sources/vj20.md)
- The inner rotor is mounted `60` degrees from the outer rotor, while each rotor's three blades are spaced `120` degrees apart. (source: sources/vj20.md)
- The paper presents the system as a shared-shaft dual-rotor arrangement with connecting structure to the central shaft. (source: sources/vj20.md)
### Spec Table

| Category | Parameter | Full-scale | Scaled-down | Status | Notes |
| --- | --- | --- | --- | --- | --- |
| Outer rotor | Rotor type | Straight-bladed H-rotor | Straight-bladed H-rotor | Source-backed | Outer rotor of proposed hybrid. (source: sources/vj20.md) |
| Outer rotor | Blade count | 3 | 3 | Source-backed | Blades equally spaced at `120 deg`. (source: sources/vj20.md) |
| Outer rotor | Blade profile | NACA0018 | NACA0018 | Source-backed | Symmetric airfoil. (source: sources/vj20.md) |
| Outer rotor | Rotor diameter | 3.854 m | 0.35 m | Source-backed | (source: sources/vj20.md) |
| Outer rotor | Rotor radius | 1.927 m | 0.175 m | Derived | Computed as diameter / 2 from source-backed values. (source: sources/vj20.md) |
| Outer rotor | Rotor height | 3.120 m | 0.283 m | Source-backed | (source: sources/vj20.md) |
| Outer rotor | Blade chord | 0.546 m | 0.0496 m | Source-backed | Constant chord. (source: sources/vj20.md) |
| Outer rotor | Pitch angle | -2.82 deg | -2.82 deg | Source-backed | (source: sources/vj20.md) |
| Inner rotor | Rotor type | Straight-bladed H-rotor | Straight-bladed H-rotor | Source-backed | Inner asymmetric-airfoil rotor. (source: sources/vj20.md) |
| Inner rotor | Blade count | 3 | 3 | Source-backed | Blades equally spaced at `120 deg`. (source: sources/vj20.md) |
| Inner rotor | Blade profile | DU 06-W-200 | DU 06-W-200 | Source-backed | Asymmetric airfoil. (source: sources/vj20.md) |
| Inner rotor | Rotor diameter | 1.578 m | 0.143 m | Source-backed | (source: sources/vj20.md) |
| Inner rotor | Rotor radius | 0.789 m | 0.0715 m | Derived | Computed as diameter / 2 from source-backed values. (source: sources/vj20.md) |
| Inner rotor | Rotor height | 1.605 m | 0.146 m | Source-backed | (source: sources/vj20.md) |
| Inner rotor | Blade chord | 0.547 m | 0.0497 m | Source-backed | Constant chord. (source: sources/vj20.md) |
| Inner rotor | Pitch angle | -3.41 deg | -3.41 deg | Source-backed | (source: sources/vj20.md) |
| Relative layout | Inner rotor phase offset | 60 deg | 60 deg | Source-backed | Inner rotor clocked `60 deg` from outer rotor. (source: sources/vj20.md) |
| Relative layout | Shared shaft | Yes | Yes | Source-backed | Both rotors coupled to central shaft. (source: sources/vj20.md) |
| Blade geometry | Straight blade | Yes | Yes | Source-backed | No helicity stated. (source: sources/vj20.md) |
| Blade geometry | Constant chord | Yes | Yes | Inference from source | Source gives one chord per rotor and does not state taper. Keep constant chord unless better source appears. (source: sources/vj20.md) |
| Blade geometry | True airfoil sections | NACA0018 and DU 06-W-200 | NACA0018 and DU 06-W-200 | Source-backed | Use actual section profiles. (source: sources/vj20.md) |
| Support hardware | Shaft diameter | 0.16 m OD | 0.0145 m OD | Recommended inference | First-pass shared main shaft size for a visually and structurally plausible CAD model; scale-down value follows the source's `11.01` length scale approximately. > Inference. |
| Support hardware | Shaft wall thickness | 0.008 m | 0.0015 m | Recommended inference | Hollow shaft assumption for a manufacturable first CAD pass. > Inference. |
| Support hardware | Outer hub diameter / thickness | 0.40 m / 0.025 m | 0.036 m / 0.0023 m | Recommended inference | Simple round hub/disc for the outer rotor strut attachment plane. > Inference. |
| Support hardware | Inner hub diameter / thickness | 0.24 m / 0.02 m | 0.0218 m / 0.0018 m | Recommended inference | Smaller round hub/disc for the inner rotor. > Inference. |
| Support hardware | Outer strut geometry | 0.08 m x 0.04 m rectangular tube | 0.0073 m x 0.0036 m rectangular tube | Recommended inference | Use 6 total struts: top and bottom support for each of the 3 outer blades. > Inference. |
| Support hardware | Inner strut geometry | 0.05 m x 0.03 m rectangular tube | 0.0045 m x 0.0027 m rectangular tube | Recommended inference | Use 6 total struts: top and bottom support for each of the 3 inner blades. > Inference. |
| Support hardware | Blade-strut attachment point | 35% chord from leading edge | 35% chord from leading edge | Recommended inference | Chosen as a clean first-pass attachment location that avoids attaching at the trailing edge. > Inference. |
| Support hardware | Bearing package | Two main radial bearings on shaft, one above and one below rotor stack | Same layout | Recommended inference | Keep support concept simple and symmetric. > Inference. |
| Support hardware | Generator mount | Coaxial lower-shaft mount below lower bearing | Same layout | Recommended inference | Match the paper's concept of a central-shaft powertrain without inventing detailed drivetrain geometry. > Inference. |

### Recommended inferred hardware specs

> Inference: the following dimensions are not provided explicitly by `vj20`. They are recommended starter values so Zookeeper can build a complete first CAD pass without freezing on unresolved support-hardware choices. They should remain editable parameters, not treated as source facts. (source: sources/vj20.md)

#### Full-scale recommended inferred hardware

- Shared main shaft outer diameter: `0.16 m`.
- Shared main shaft wall thickness: `0.008 m`.
- Outer rotor hub diameter: `0.40 m`.
- Outer rotor hub thickness: `0.025 m`.
- Inner rotor hub diameter: `0.24 m`.
- Inner rotor hub thickness: `0.02 m`.
- Outer rotor struts: `6` total, using rectangular tube `0.08 m x 0.04 m`.
- Inner rotor struts: `6` total, using rectangular tube `0.05 m x 0.03 m`.
- Blade-to-strut attachment target: `35%` chord from leading edge.
- Support layout: one upper and one lower strut per blade for both rotors.
- Bearing layout: `2` main shaft bearings, one above the upper rotor support plane and one below the lower rotor support plane.
- Generator mount concept: coaxial lower-shaft cylindrical mount below the lower bearing.

#### Scaled-down recommended inferred hardware

- Shared main shaft outer diameter: `0.0145 m`.
- Shared main shaft wall thickness: `0.0015 m`.
- Outer rotor hub diameter: `0.036 m`.
- Outer rotor hub thickness: `0.0023 m`.
- Inner rotor hub diameter: `0.0218 m`.
- Inner rotor hub thickness: `0.0018 m`.
- Outer rotor struts: `6` total, using rectangular tube `0.0073 m x 0.0036 m`.
- Inner rotor struts: `6` total, using rectangular tube `0.0045 m x 0.0027 m`.
- Blade-to-strut attachment target: `35%` chord from leading edge.
- Bearing layout: same two-bearing concept as full-scale.
- Generator mount concept: same coaxial lower-shaft concept as full-scale.

#### How to use these inferred values

- Treat them as editable defaults, not as source-backed facts.
- Keep the rotor diameters, heights, chords, blade counts, airfoils, pitch angles, and `60 deg` phase offset fixed to the source values while adjusting hardware.
- If Zookeeper has trouble with tiny scaled-down wall thicknesses, prioritize preserving the outer geometry and increase only the inferred support thicknesses.
- If a cleaner visual model is preferred, the hubs can be simplified to flat circular plates and the struts to plain rectangular beams without changing the source-backed rotor geometry.

## Modeling notes

- Figure `1` is the best source for the conceptual layout and the idea of outer symmetric plus inner asymmetric blades. (source: sources/vj20.md)
- Figure `2` is the best source for the CAD-like appearance of the scaled-down arrangement. (source: sources/vj20.md)
- Figure `3` is useful only as a rough test-fixture sanity check, not as a geometric source for the final turbine. (source: sources/vj20.md)
- The source later compares rough and smooth blade surfaces, but explicitly says smoothing caused negligible dimensional or profile change, so surface roughness should not become a geometry change in the main CAD. (source: sources/vj20.md)

## Detailed Zookeeper Prompt
\***fairly significantly shortened by Anna

```text
Create a concentric dual-H-rotor vertical-axis wind turbine with the geometry detailed below. It should be fully parameterized so a scaled-down variant can be generated later.

- an outer 3-blade H-rotor using symmetric NACA0018 blades
- an inner 3-blade H-rotor using asymmetric DU 06-W-200 blades
- both rotors mounted on a common vertical central shaft
- the inner rotor phase-shifted 60 degrees relative to the outer rotor
- Z axis = vertical shaft axis
- XY plane = rotor plan view

Outer rotor geometry:
- Rotor type: straight-bladed H-rotor
- Blade count: 3
- Blade profile: NACA0018
- Rotor diameter: 3.854 m
- Rotor radius: 1.927 m
- Rotor height: 3.120 m
- Blade chord: 0.546 m
- Pitch angle: -2.82 deg
- Blade spacing: equally spaced at 120 deg
(source: sources/vj20.md)

Inner rotor geometry:
- Rotor type: straight-bladed H-rotor
- Blade count: 3
- Blade profile: DU 06-W-200
- Rotor diameter: 1.578 m
- Rotor radius: 0.789 m
- Rotor height: 1.605 m
- Blade chord: 0.547 m
- Pitch angle: -3.41 deg
- Blade spacing: equally spaced at 120 deg within the inner rotor
- Whole inner rotor clocked 60 deg from the outer rotor
(source: sources/vj20.md)

Blade modeling rules:
- Use true airfoil sections for NACA0018 and DU 06-W-200
- Model blades as straight, constant-chord, vertically extruded airfoils
- No helical twist
- No variable chord
- No blade taper stated by the source
- No variable pitch mechanism unless added as a separate speculative concept

Assembly/layout rules:
- Build both rotors concentrically around one shared vertical shaft
- Use top and bottom support members/struts to connect blades to the shaft in standard H-rotor fashion
- Keep the outer rotor surrounding the inner rotor with clear radial separation
- Match the overall visual arrangement to the attached image.


Infer using industry standard parts of reasonable sizes:
- shaft diameter
- hub diameter and thickness
- strut cross-sections
- strut attachment points along the chord
- bearing geometry
- generator and battery mounting geometry
- fasteners/joints dimensions

Inference instructions:
- Choose the simplest manufacturable support structure that preserves the specified geometry
- Prefer tubular or flat-bar struts with minimal visual clutter
- Keep the support structure symmetric and compact
- Do not let inferred support hardware alter the stated rotor diameters, heights, blade counts, pitch angles, or 60 deg offset
- Output a short assumptions list naming every inferred dimension

Confirm before finalizing that:
- outer rotor has 3 NACA0018 blades
- inner rotor has 3 DU 06-W-200 blades
- both are straight-bladed H-rotors
- both are concentric on one vertical shaft
- outer rotor D/H/chord/pitch match given dimensions
- inner rotor D/H/chord/pitch match given dimensions
- inner rotor is phase-shifted 60 deg relative to outer rotor
```

### Results:
**Mode:** Thoughtful      **Time:** 9 min
**Notes:** oops forgot to give it the picture

![[Pasted image 20260710115544.png|335]]
![[Pasted image 20260710115517.png|333]]

**Response:**
```text
Done — I created and validated the parameterized dual-H-rotor VAWT assembly.

**Files created/updated**
- `parameters.kcl` — all source and inferred dimensions, with `modelScale = 1`
- `outerBladeNaca0018.kcl` — straight constant-chord NACA0018 blade
- `innerBladeDu06W200.kcl` — straight constant-chord DU06-W-200 blade
- `main.kcl` — concentric assembly with shaft, hubs, bearings, generator, battery mount, struts, pads, and fasteners

I did not find the referenced attachment or `sources/vj20.md` in the workspace, so I used the dimensions from your prompt. The airfoil sections are modeled from Selig-format coordinate data as fully constrained solver-line polylines, using NACA0018 and DU06-W-200 coordinate sources. 

**Validation completed**
- KCL executes successfully.
- All generated sketches are fully constrained.
- Final visual checks confirm:
  - outer rotor has **3 NACA0018 blades**
  - inner rotor has **3 DU06-W-200 blades**
  - both are **straight-bladed H-rotors**
  - both are **concentric on one shared vertical Z shaft**
  - outer rotor: **D 3.854 m / R 1.927 m / H 3.120 m / chord 0.546 m / pitch -2.82°**
  - inner rotor: **D 1.578 m / R 0.789 m / H 1.605 m / chord 0.547 m / pitch -3.41°**
  - inner rotor is **phase-shifted 60°** relative to the outer rotor

**Assumptions / inferred dimensions**
- Rotor radius is the **blade quarter-chord / pitch-axis radius**.
- Inner rotor is vertically centered in the outer rotor: bottom `0.7575 m`, top `2.3625 m`.
- Shaft: `70 mm` diameter, `76 mm` clearance bores, from `-0.500 m` to `3.420 m`.
- Outer hubs: `320 mm` OD × `80 mm` thick.
- Inner hubs: `220 mm` OD × `60 mm` thick.
- Outer struts: `70 mm` wide × `50 mm` thick.
- Inner struts: `50 mm` wide × `35 mm` thick.
- Outer blade joint pads: `120 mm` diameter × `30 mm` thick.
- Inner blade joint pads: `90 mm` diameter × `25 mm` thick.
- Fastener heads: `30 mm` diameter × `12 mm` high.
- Bearing housings: `180 mm` OD × `76 mm` bore × `70 mm` thick.
- Generator: `560 mm` OD × `86 mm` bore × `320 mm` high.
- Base plate: `1050 × 750 × 45 mm`.
- Battery pack: `420 × 220 × 160 mm`, offset `390 mm` in X and `-210 mm` in Y.
- Battery tray: battery footprint plus `40 mm`, `20 mm` thick.

Possible next edits:
1. Increase the airfoil polyline density to use the full DAT point sets.
2. Add a cutaway/ghosted view option so the inner rotor is always visible.
3. Add a simple exploded assembly variant for clearer documentation.
```


## Short Production-Ready Zookeeper Prompt

```text
Model the proposed hybrid VAWT as a parameterized concentric dual-H-rotor CAD assembly based only on given geometry. Use one shared vertical shaft, three outer straight `NACA0018` blades, and three inner straight `DU 06-W-200` blades. The inner rotor must be phase-shifted `60 deg` from the outer rotor, and each rotor's three blades must be spaced `120 deg` apart.

Build the full-scale configuration first with these exact values:
- outer rotor diameter `3.854 m`, height `3.120 m`, chord `0.546 m`, pitch `-2.82 deg`
- inner rotor diameter `1.578 m`, height `1.605 m`, chord `0.547 m`, pitch `-3.41 deg`

Then create a scaled-down configuration with these exact values:
- outer rotor diameter `0.35 m`, height `0.283 m`, chord `0.0496 m`, pitch `-2.82 deg`
- inner rotor diameter `0.143 m`, height `0.146 m`, chord `0.0497 m`, pitch `-3.41 deg`

Rules:
- use true `NACA0018` and `DU 06-W-200` airfoil sections
- blades must be straight, constant-chord, and vertically extruded
- do not add a Savonius rotor, helicity, taper, variable pitch, shrouds, or guide vanes
- infer shaft, hub, strut, bearing, and generator-mount dimensions conservatively and label them clearly as inferred
- do not let inferred hardware change any source-stated rotor geometry

Deliver:
- full-scale CAD assembly
- scaled-down CAD configuration
- top view, front view, isometric render
- short assumptions list
- parameter table separating source-backed dimensions from inferred ones
```

### Results:
**Mode:** Thoughtful      **Time:** 15 min
**Notes:** seems to have done a better job with a less overwhelming prompt, I don't see any glaring errors like the disconnected blades of the previous prompt

![[Pasted image 20260710121856.png|352]]
![[Pasted image 20260710121823.png|353]]
**Response:**
```text
Completed. The project now contains:

- **`main.kcl`** — full-scale concentric dual-H-rotor VAWT assembly.
- **`scaledConfiguration.kcl`** — scaled-down configuration.
- Reusable unit part files for the airfoils, shaft, hubs, bearings, struts, and generator mount.

I used solver-sketch polyline airfoil traces from source coordinate sets: **NACA 0018** from AirfoilTools/UIUC and **DU06-W-200** from the BigFoil Selig DAT listing. 

Validation completed:
- All sketch files are **fully constrained**.
- Lint/format pass.
- `main.kcl` and `scaledConfiguration.kcl` both execute successfully.
- Captured **top, front, and isometric** render checks for both configurations.
- Captured direct top-view checks of the NACA0018 and DU06-W-200 unit airfoil sections.

### Short assumptions

1. Rotor diameter is measured to each blade’s **quarter-chord pitch/attachment axis**.
2. Blades are straight, constant-chord, vertically extruded, and centered about `Z = 0`.
3. The inner rotor is placed at **60 deg phase offset** from the outer rotor; all three-blade sets are spaced **120 deg**.
4. Shaft, hubs, struts, bearings, and generator mount are conservative inferred envelopes only and are named `inferred...` in KCL.
5. No Savonius rotor, helicity, taper, variable pitch, shroud, or guide vanes were added.

### Source-backed parameter table

| Configuration | Rotor | Airfoil | Diameter | Radius | Height | Chord | Pitch | Blade count / phase |
|---|---:|---|---:|---:|---:|---:|---:|---|
| Full-scale | Outer | NACA0018 | 3.854 m | 1.927 m | 3.120 m | 0.546 m | -2.82 deg | 3 blades @ 120 deg |
| Full-scale | Inner | DU 06-W-200 | 1.578 m | 0.789 m | 1.605 m | 0.547 m | -3.41 deg | 3 blades @ 120 deg, +60 deg phase |
| Scaled-down | Outer | NACA0018 | 0.350 m | 0.175 m | 0.283 m | 0.0496 m | -2.82 deg | 3 blades @ 120 deg |
| Scaled-down | Inner | DU 06-W-200 | 0.143 m | 0.0715 m | 0.146 m | 0.0497 m | -3.41 deg | 3 blades @ 120 deg, +60 deg phase |

### Inferred hardware table

| Configuration | Item | Inferred dimensions |
|---|---|---:|
| Full-scale | Shared shaft | Ø0.080 m × 3.720 m |
| Full-scale | Generator mount | Ø0.550 m × 0.180 m |
| Full-scale | Bearings | Ø0.220 m × 0.120 m, top/bottom |
| Full-scale | Outer hub collars | Ø0.400 m × 0.120 m |
| Full-scale | Inner hub collars | Ø0.300 m × 0.100 m |
| Full-scale | Outer struts | 0.060 m wide × 0.045 m thick |
| Full-scale | Inner struts | 0.040 m wide × 0.035 m thick |
| Scaled-down | Shared shaft | Ø0.012 m × 0.353 m |
| Scaled-down | Generator mount | Ø0.085 m × 0.020 m |
| Scaled-down | Bearings | Ø0.033 m × 0.012 m, top/bottom |
| Scaled-down | Outer hub collars | Ø0.060 m × 0.012 m |
| Scaled-down | Inner hub collars | Ø0.045 m × 0.010 m |
| Scaled-down | Outer struts | 0.006 m wide × 0.0045 m thick |
| Scaled-down | Inner struts | 0.0045 m wide × 0.0035 m thick |

Suggested next edits:
1. Add dimension-reference construction rings for rotor diameters.
2. Add bolt-hole patterns to the generator mount and hub collars.
3. Densify the DU 06-W-200 airfoil trace if you want a higher-resolution CAD section.
```

