---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[ca3]]"
  - "[[ca4]]"
  - "[[ca6]]"
  - "[[ca15]]"
  - "[[ca21]]"
  - "[[cj7]]"
Source_count: 6
tags:
  - cfd
---
# SimScale VAWT Rotating Region

## What a rotating region is

SimScale provides rotating zones to model rotating systems including turbines. The two documented rotating-zone types are MRF (Multiple Reference Frame) and AMI (Arbitrary Mesh Interface). (source: sources/ca15.md)

The `cj7` rotating-drone tutorial provides a concrete documented example of the `MRF rotating zone` option applied to a cylindrical rotating subregion around a propeller. (source: sources/cj7.md)

For incompressible analysis, rotating zones are available under Advanced concepts. Solid-body motion is also available there only for transient incompressible analysis. (source: sources/ca15.md)

> Unverified: Which of MRF, AMI, or solid-body motion is appropriate for a particular VAWT objective. The captured source names the options but does not provide their selection criteria or detailed configuration steps. (source: sources/ca15.md)

## CAD preparation sequence

1. Prepare the turbine CAD and simplify irrelevant small features before creating the simulation fluid region. (source: sources/ca3.md)
2. Create the external fluid volume around the turbine. (source: sources/ca4.md)
3. Create a cylinder enclosing the rotating rotor. The custom-cylinder operation requires rotation center, axis, radius, and height; the from-faces option instead encloses selected faces. (source: sources/ca4.md)
4. When symmetry is available, reduce the modeled geometry first so the rotating cylinder only encloses the simulated fraction of the rotor system. The `cj7` example uses two symmetry planes and only one-quarter of the drone. (source: sources/cj7.md)
5. For a from-faces cylinder, use SimScale's documented `1.1` clearance-factor recommendation for rotating machinery. (source: sources/ca4.md)
6. Check that solids do not interfere or overlap, because these can cause geometry-operation and meshing failures. (source: sources/ca4.md)
7. Update the assigned simulation geometry manually after CAD changes. (source: sources/ca4.md)

## Turn the cylinder into a usable zone

Creating the CAD cylinder alone does not assign rotating physics. During hex-dominant meshing, assign a closed volume to a surface refinement and enable cell-zone creation; the resulting enclosed cells can be used for MRF or AMI rotating regions. (source: sources/ca21.md)

The `cj7` tutorial adds that with SimScale's standard physics-based meshing, the platform automatically creates the necessary cell zones for the rotating volume. (source: sources/cj7.md)

Check that the assigned volume is closed. SimScale states that a closed volume is required for cell-zone creation. (source: sources/ca21.md)

## Practical checks

- Confirm the cylinder encloses the intended rotor geometry without accidentally including unrelated stationary geometry. > Inference: a cell zone assigns properties to all enclosed cells, so its extent determines where the rotating-zone property applies. (source: sources/ca21.md)
- Confirm the physical rotation axis and direction before running. The CAD cylinder's custom method explicitly requires an axis of rotation. (source: sources/ca4.md)
- Refine the mesh where needed around the rotor and rotating-zone boundary; region and surface refinements are available for local mesh control. (source: sources/ca21.md)
- For tetrahedral standard-mesh cases, the `cj7` documentation explicitly raises the number of non-orthogonal correctors to `4` to improve solver behavior on that mesh. (source: sources/cj7.md)

Related pages: [[SimScale VAWT CFD Learning Path]], [[SimScale VAWT Mesh and Quality]], [[SimScale VAWT Transient Runs and Outputs]].
