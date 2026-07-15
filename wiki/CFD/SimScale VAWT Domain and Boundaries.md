---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[ca4]]"
  - "[[ca6]]"
  - "[[ca12]]"
  - "[[ca13]]"
  - "[[ca14]]"
  - "[[ca21]]"
  - "[[cj6]]"
Source_count: 7
tags:
  - cfd
---
# SimScale VAWT Domain and Boundaries

## Fluid domain

An external aerodynamic CFD case needs a fluid volume surrounding the turbine. SimScale's CAD Edit creates an external flow volume from user-specified minimum and maximum dimensions in the three coordinate directions. (source: sources/ca4.md)

For external hex-dominant meshing, SimScale gives a general domain guideline of at least `2-3D` upstream, `6-8D` downstream, and `2-3D` laterally, where `D` is the object's reference length. (source: sources/ca21.md)

The `cj6` building-wind tutorial adds a practical vertical-domain reminder: keep enough head space above the object so accelerated flow over the top is still captured within the computational volume. (source: sources/cj6.md)

> Uncertainty: this is broad external-aerodynamics guidance, not a VAWT validation rule. The documentation does not define the appropriate VAWT reference length or prove that these extents remove VAWT blockage and wake-boundary effects. (source: sources/ca21.md)

## Essential assignments

- Choose the fluid material and its relevant properties. In incompressible analysis, material selection is part of the setup. (source: sources/ca6.md, sources/ca12.md)
- Set initial pressure and velocity fields close to the expected solution, or consider potential-flow initialization if convergence or early-step stability is problematic. (source: sources/ca6.md)
- Add boundary conditions to faces: SimScale describes a boundary condition as a type, one or more face assignments, and values. (source: sources/ca14.md)
- Assign all required variables on every boundary. In incompressible analysis, an unassigned face defaults to a no-slip wall with a turbulence wall function. (source: sources/ca6.md)

## Boundary-condition review

Before meshing or running, list every outer-domain face and every turbine surface, then verify its intended assignment in the boundary-condition visualization. > Inference: SimScale supplies face-based boundary assignments and a visualization tool specifically to help users understand and explain configurations. (source: sources/ca14.md)

Available CFD boundary-condition types include velocity inlet/outlet, pressure inlet/outlet, wall, symmetry, periodic, and atmospheric-boundary-layer inlet. Their availability depends on the analysis type. (source: sources/ca14.md)

The `cj6` example uses one velocity-inlet face, pressure outlets on the remaining exposed outer faces, and wall assignments for the ground and obstacle geometry. (source: sources/cj6.md)

> Unverified: The correct inlet, outlet, lateral, top, bottom, and blade-wall assignments for a specific VAWT case. These depend on the target physical scenario and are not assembled into a VAWT procedure by the captured documentation. (source: sources/ca14.md, sources/ca25.md, sources/ca26.md)

## CAD pitfalls

- Check CAD units before setup; unit discrepancies can produce unrealistic dimensions, and SimScale's default Workbench unit is meters. (source: sources/ca3.md)
- Remove small manufacturing details that do not affect the target flow because they can increase meshing and compute time, and remove small sharp faces that can make surface meshing fail. (source: sources/ca3.md)
- Check for interferences before meshing; overlapping solids can cause meshing failure. (source: sources/ca4.md)

Related pages: [[SimScale VAWT CFD Learning Path]], [[SimScale VAWT Rotating Region]], [[SimScale VAWT Mesh and Quality]].
