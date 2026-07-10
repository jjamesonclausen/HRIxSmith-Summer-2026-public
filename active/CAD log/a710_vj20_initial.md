---
Created: 2026-07-10
Updated: 2026-07-10
Sources:
  - "[[vj20]]"
tags:
  - active
  - cad-log
---

# a710 vj20 Initial

This note packages the source-grounded CAD brief for recreating the `vj20` proposed hybrid VAWT as a dual-H-type turbine assembly. It includes:

- a detailed Zookeeper prompt
- a shorter production-ready Zookeeper prompt
- a spec table separating source-backed geometry from inferred items

The source gives enough to model the overall dual-H-rotor layout, blade profiles, blade counts, diameters, heights, chords, pitch angles, and the `60` degree phase offset between inner and outer rotors, but it does not fully dimension the shaft, struts, hubs, bearings, or generator hardware. So the correct CAD target is a source-faithful geometry recreation with clearly labeled inferred support structure. (source: sources/vj20.md)

## What the source supports

- The proposed turbine is a hybrid VAWT with an outer straight-bladed H-rotor and an inner asymmetric-airfoil H-rotor replacing the usual Savonius starter. (source: sources/vj20.md)
- The outer rotor uses three `NACA0018` blades. (source: sources/vj20.md)
- The inner rotor uses three `DU 06-W-200` blades. (source: sources/vj20.md)
- The inner rotor is mounted `60` degrees from the outer rotor, while each rotor's three blades are spaced `120` degrees apart. (source: sources/vj20.md)
- The paper presents the system as a shared-shaft dual-rotor arrangement with connecting structure to the central shaft. (source: sources/vj20.md)

## Source-backed geometry summary

### Full-scale model

- Outer rotor diameter: `3.854 m` (source: sources/vj20.md)
- Outer rotor height: `3.120 m` (source: sources/vj20.md)
- Outer blade chord: `0.546 m` (source: sources/vj20.md)
- Outer blade profile: `NACA0018` (source: sources/vj20.md)
- Outer blade count: `3` (source: sources/vj20.md)
- Outer blade pitch angle: `-2.82 deg` (source: sources/vj20.md)
- Inner rotor diameter: `1.578 m` (source: sources/vj20.md)
- Inner rotor height: `1.605 m` (source: sources/vj20.md)
- Inner blade chord: `0.547 m` (source: sources/vj20.md)
- Inner blade profile: `DU 06-W-200` (source: sources/vj20.md)
- Inner blade count: `3` (source: sources/vj20.md)
- Inner blade pitch angle: `-3.41 deg` (source: sources/vj20.md)
- Inner rotor phase offset from outer rotor: `60 deg` (source: sources/vj20.md)

### Scaled-down model

- Outer rotor diameter: `0.35 m` (source: sources/vj20.md)
- Outer rotor height: `0.283 m` (source: sources/vj20.md)
- Outer blade chord: `0.0496 m` (source: sources/vj20.md)
- Outer blade profile: `NACA0018` (source: sources/vj20.md)
- Outer blade count: `3` (source: sources/vj20.md)
- Outer blade pitch angle: `-2.82 deg` (source: sources/vj20.md)
- Inner rotor diameter: `0.143 m` (source: sources/vj20.md)
- Inner rotor height: `0.146 m` (source: sources/vj20.md)
- Inner blade chord: `0.0497 m` (source: sources/vj20.md)
- Inner blade profile: `DU 06-W-200` (source: sources/vj20.md)
- Inner blade count: `3` (source: sources/vj20.md)
- Inner blade pitch angle: `-3.41 deg` (source: sources/vj20.md)
- Inner rotor phase offset from outer rotor: `60 deg` (source: sources/vj20.md)

## Detailed Zookeeper Prompt

```text
Recreate the proposed dual-H-type hybrid VAWT from the paper "Experimental investigation and analysis of proposed hybrid vertical axis wind turbine design" as a clean, parameterized CAD assembly. Base the geometry only on the source-backed dimensions and layout below, and clearly flag any inferred dimensions or support hardware. (source: sources/vj20.md)

Goal:
Create a concentric dual-H-rotor vertical-axis wind turbine with:
- an outer 3-blade H-rotor using symmetric NACA0018 blades
- an inner 3-blade H-rotor using asymmetric DU 06-W-200 blades
- both rotors mounted on a common vertical central shaft
- the inner rotor phase-shifted 60 degrees relative to the outer rotor
This is the paper's replacement for a typical inner Savonius starter: it is a dual-H-type hybrid, not a Savonius-Darrieus hybrid. (source: sources/vj20.md)

Primary modeling target:
Build the full-scale turbine as the main CAD assembly using the optimized geometry from Table 2. Also make the model fully parameterized so a scaled-down variant can be generated from Table 4 afterward. (source: sources/vj20.md)

Coordinate system:
- Z axis = vertical shaft axis
- XY plane = rotor plan view
- Wind direction for renders can be along +X
(source: sources/vj20.md)

Full-scale outer rotor geometry:
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

Full-scale inner rotor geometry:
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
(source: sources/vj20.md)

Assembly/layout rules:
- Build both rotors concentrically around one shared vertical shaft
- Use top and bottom support members/struts to connect blades to the shaft in standard H-rotor fashion
- Keep the outer rotor surrounding the inner rotor with clear radial separation
- Match the overall visual arrangement to the paper's conceptual figure and scaled CAD figure as closely as possible
(source: sources/vj20.md)

Visual references to match:
- Figure 1 for the overall operating concept of the hybrid rotor with inner asymmetric blades and outer symmetric blades
- Figure 2 for the general CAD-like arrangement of the scaled-down model
- Figure 3 only as a sanity check for how the test article sits on a shaft in a bracket, not as a source of exact turbine dimensions
(source: sources/vj20.md)

What is explicitly known vs inferred:
Known from source:
- blade counts
- airfoil choices
- full-scale diameters, heights, chords, and pitch angles
- scaled-down diameters, heights, chords, and pitch angles
- 60 deg phase offset between inner and outer rotors
- common central-shaft architecture
(source: sources/vj20.md)

Not fully specified by source, so infer conservatively and label as inferred:
- shaft diameter
- hub diameter and thickness
- exact strut cross-sections
- exact strut attachment points along the chord
- exact bearing geometry
- exact generator and battery mounting geometry
- exact fasteners/joints dimensions
(source: sources/vj20.md)

Inference instructions:
- Choose the simplest manufacturable support structure that preserves the source geometry
- Prefer tubular or flat-bar struts with minimal visual clutter
- Keep the support structure symmetric and compact
- Do not let inferred support hardware alter the source-stated rotor diameters, heights, blade counts, pitch angles, or 60 deg offset
- Output a short assumptions list naming every inferred dimension
(source: sources/vj20.md)

Scaled-down variant:
After the full-scale model is complete, create a second configuration for the scaled-down test model using Table 4:
- Outer rotor diameter: 0.35 m
- Outer rotor height: 0.283 m
- Outer blade chord: 0.0496 m
- Outer blade profile: NACA0018
- Outer blade count: 3
- Outer pitch angle: -2.82 deg
- Inner rotor diameter: 0.143 m
- Inner rotor height: 0.146 m
- Inner blade chord: 0.0497 m
- Inner blade profile: DU 06-W-200
- Inner blade count: 3
- Inner pitch angle: -3.41 deg
- Preserve the same 60 deg rotor phase offset
(source: sources/vj20.md)

Important exclusions:
- Do not add a Savonius rotor
- Do not convert it into a helical turbine
- Do not change blade count
- Do not "improve" the geometry beyond the paper
- Do not invent aero fairings, guide vanes, shrouds, or variable pitch unless separated into an optional concept file
(source: sources/vj20.md)

Optional test-article note:
If you want to reflect the paper's prototype context, note that the scaled-down model was developed using 3D fused deposition modeling followed by aluminum casting, but this is a manufacturing note, not a geometry change. (source: sources/vj20.md)

Optional surface-finish note:
The source later compares rough and smooth blade surfaces, but says smoothing caused negligible dimensional/profile change. So do not encode roughness as a geometry change in the main CAD unless making a separate visualization or manufacturing note. (source: sources/vj20.md)

Deliverables:
- Full-scale CAD assembly
- Scaled-down CAD configuration
- Isometric render
- Front elevation
- Top view showing 120 deg blade spacing and 60 deg inner-to-outer phase shift
- Short assumptions list for inferred shaft/strut/hub dimensions
- Parameter table listing all source-backed dimensions separately from inferred ones
(source: sources/vj20.md)

Verification checklist:
Confirm before finalizing that:
- outer rotor has 3 NACA0018 blades
- inner rotor has 3 DU 06-W-200 blades
- both are straight-bladed H-rotors
- both are concentric on one vertical shaft
- outer rotor D/H/chord/pitch match Table 2
- inner rotor D/H/chord/pitch match Table 2
- inner rotor is phase-shifted 60 deg relative to outer rotor
- scaled configuration matches Table 4
(source: sources/vj20.md)
```

## Short Production-Ready Zookeeper Prompt

```text
Model the `vj20` proposed hybrid VAWT as a parameterized concentric dual-H-rotor CAD assembly based only on source-backed geometry. Use one shared vertical shaft, three outer straight `NACA0018` blades, and three inner straight `DU 06-W-200` blades. The inner rotor must be phase-shifted `60 deg` from the outer rotor, and each rotor's three blades must be spaced `120 deg` apart. (source: sources/vj20.md)

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
(source: sources/vj20.md)
```

## Spec Table

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

## Recommended first-pass inferred hardware specs

> Inference: the following dimensions are not provided explicitly by `vj20`. They are recommended starter values so Zookeeper can build a complete first CAD pass without freezing on unresolved support-hardware choices. They should remain editable parameters, not treated as source facts. (source: sources/vj20.md)

### Full-scale recommended inferred hardware

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

### Scaled-down recommended inferred hardware

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

### How to use these inferred values

- Treat them as editable defaults, not as source-backed facts.
- Keep the rotor diameters, heights, chords, blade counts, airfoils, pitch angles, and `60 deg` phase offset fixed to the source values while adjusting hardware.
- If Zookeeper has trouble with tiny scaled-down wall thicknesses, prioritize preserving the outer geometry and increase only the inferred support thicknesses.
- If a cleaner visual model is preferred, the hubs can be simplified to flat circular plates and the struts to plain rectangular beams without changing the source-backed rotor geometry.

## Modeling notes

- Figure `1` is the best source for the conceptual layout and the idea of outer symmetric plus inner asymmetric blades. (source: sources/vj20.md)
- Figure `2` is the best source for the CAD-like appearance of the scaled-down arrangement. (source: sources/vj20.md)
- Figure `3` is useful only as a rough test-fixture sanity check, not as a geometric source for the final turbine. (source: sources/vj20.md)
- The source later compares rough and smooth blade surfaces, but explicitly says smoothing caused negligible dimensional or profile change, so surface roughness should not become a geometry change in the main CAD. (source: sources/vj20.md)

## Uncertainty

- The source does not fully specify shaft diameter, hub geometry, strut thickness or shape, bearing geometry, fastener details, or generator mount dimensions. These must be inferred and labeled clearly in any CAD output. (source: sources/vj20.md)
- The source reports multiple startup-related values depending on context: `2.81 m/s`, `1.405 m/s`, `1.72 m/s`, and `1.54 m/s`. These are useful performance notes but do not affect the rotor geometry in this note. (source: sources/vj20.md)
- The recommended hardware specs above are a practical first-pass modeling choice only. They are intended to unblock CAD work, not to claim structural optimization or source validation. (source: sources/vj20.md)

## Next check

- If this gets handed to Zookeeper, review the returned top view first to confirm the `120 deg` blade spacing and `60 deg` inner-to-outer phase offset before spending time on detailed supports.
