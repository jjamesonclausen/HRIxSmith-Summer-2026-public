---
Sources:
  - "[[HRI2526]]"
  - "[[va29]]"
  - "[[va30]]"
tags:
  - "#validation"
  - cad
---

### Rotor Geometry
[[va29]] does not provide enough exact geometry information to recreate the classical rotor reliably:
- Blade wall thickness for the primary d = 0.68 m, s/d = 0.1 validation rotor.
- Rotor height or the exact aspect ratio used for the classical-validation power curve.
- Endplate diameter/thickness and shaft geometry.
- Exact blade cross-section construction and blade-to-endplate connections.
- Inlet turbulence quantities and complete material/solver/discretization settings.
- Number of simulated revolutions before averaging, beyond stating that a two-revolution average was used. (source: sources/va29.md)

For your prompt, specify that the model is an assumed classical two-bucket Savonius rotor with D = 0.68 m, s/D = 0.10, then explicitly flag all missing geometry as assumptions. Do not call the result validated until it agrees with the experimental data used by the paper.

### Zookeeper prompt:
Create a parametric aerodynamic CAD model named “Classical Savonius - va29/va30 Benchmark”.

Purpose:
Recreate the two-bucket classical Savonius geometry cited by va29 for CFD validation, using the experimental geometry in va30. Model only the bucket geometry. Do not invent shaft, hub, endplate, bearing, support, or wall-thickness dimensions.

Units: meters.

Parameters:
- bucket_radius = 0.250
- bucket_diameter = 0.500
- rotor_height = 1.000
- gap_ratio = 0.10
- inside_edge_gap = 0.050
- nominal_rotor_diameter = 1.000
- bucket_arc_angle = 180 deg
- rotation_axis = global Z axis through the origin

Geometry:
1. Create two identical vertical semicircular Savonius buckets.
2. Each bucket is a 180-degree circular arc with radius 0.250 m.
3. Extrude each bucket uniformly to a height of 1.000 m along global Z.
4. Arrange the buckets in the standard opposed Savonius configuration shown in Figure 2 of va30:
   - Their concave faces oppose one another.
   - Their straight diameter edges are vertical.
   - The closest inside edges are separated by 0.050 m.
   - Place the global Z rotation axis at the midpoint of that inside-edge gap.
   - Orient the buckets so the assembly has a nominal outside rotor diameter of 1.000 m.
5. Keep the two buckets as separate named bodies: `Bucket_A` and `Bucket_B`.
6. Add named reference geometry only:
   - `Rotation_Axis`: global Z axis
   - `Rotor_Midplane`: XY plane at Z = 0.500 m
   - `Swept_Diameter`: 1.000 m reference circle or dimension
7. Do not add endplates, a shaft, hubs, fasteners, supports, fillets, wall thickness, or manufacturing features.
8. Export a clean STEP model with the two bucket bodies and reference axis preserved.

Validation checks:
- Exactly two bucket bodies exist.
- Each bucket is 1.000 m tall.
- Each bucket profile is a 180-degree semicircle of 0.250 m radius.
- Inside-edge gap is 0.050 m.
- Global Z is the rotation axis.
- Report all parameter values and flag any geometry that cannot be created without assumptions.
This recreates the experimentally documented aerodynamic bucket layout. Endplate, shaft, and wall-thickness dimensions are not specified in the sources, so the prompt correctly excludes them. (source: sources/va29.md, sources/va30.md)
