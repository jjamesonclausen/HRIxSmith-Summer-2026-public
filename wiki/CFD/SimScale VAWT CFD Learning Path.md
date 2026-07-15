---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[ca3]]"
  - "[[ca5]]"
  - "[[ca6]]"
  - "[[ca7]]"
  - "[[ca8]]"
  - "[[ca12]]"
  - "[[ca13]]"
  - "[[ca14]]"
  - "[[ca15]]"
  - "[[ca16]]"
  - "[[ca17]]"
  - "[[ca18]]"
  - "[[ca19]]"
  - "[[ca20]]"
  - "[[ca21]]"
  - "[[ca22]]"
  - "[[ca23]]"
  - "[[ca24]]"
Source_count: 18
tags:
  - cfd
---
# SimScale VAWT CFD Learning Path

Use this as the order for learning SimScale while building a first VAWT aerodynamic case. It is a setup map, not a validated VAWT recipe. (source: sources/ca3.md, sources/ca6.md, sources/ca7.md)

## 1. Define the question

- State the rotor, wind condition, rotational condition, and quantity to compare before touching the setup. > Inference: this keeps the CAD, mesh, result controls, and later design comparison aligned; the documentation requires these setup elements but does not prescribe a VAWT study question. (source: sources/ca3.md, sources/ca6.md, sources/ca19.md)
- Select an analysis type whose assumptions match the intended physics. Incompressible analysis applies when density variations are negligible, which SimScale describes as typical when velocities and temperature gradients are small. (source: sources/ca6.md)

## 2. Prepare geometry

- Upload the CAD, check units, remove features that do not affect the intended flow result, and resolve CAD faults before meshing. (source: sources/ca3.md)
- Create an external fluid volume because CFD solves the fluid volume, not the solid turbine itself. (source: sources/ca4.md)
- Create a separate cylindrical volume around the rotor if the case will use a rotating zone. SimScale recommends a clearance factor of `1.1` when a cylinder is created from faces for rotating machinery. (source: sources/ca4.md)
- After CAD Edit changes, manually update the simulation geometry; SimScale does not automatically apply CAD modifications to the assigned simulation. (source: sources/ca4.md)

See [[SimScale VAWT Rotating Region]] and [[SimScale VAWT Domain and Boundaries]].

## 3. Define the physics and boundaries

- In an incompressible analysis, set a turbulence model, time dependency, algorithm, material, initial conditions, and boundary conditions. (source: sources/ca6.md)
- Use transient analysis when the time-dependent flow solution is the quantity of interest; steady simulations are less computationally demanding but return a converged steady-state solution. (source: sources/ca8.md)
- Assign every required variable on every boundary. An unassigned face in an incompressible analysis defaults to a no-slip wall with a turbulence wall function, so unintentional omissions can change the case. (source: sources/ca6.md)

See [[SimScale VAWT Domain and Boundaries]] and [[SimScale VAWT Transient Runs and Outputs]].

## 4. Mesh, then inspect it

- SimScale offers standard, hex-dominant, and hex-dominant parametric meshers for incompressible analysis. (source: sources/ca6.md)
- Hex-dominant external meshing is intended for aerodynamic flow around bodies, and its automatic mode is appropriate for a preliminary run before detailed mesh tuning. (source: sources/ca21.md)
- Inspect the completed mesh and its quality metrics before trusting a run; mesh density and quality affect accuracy and stability. (source: sources/ca22.md)

See [[SimScale VAWT Mesh and Quality]].

## 5. Plan outputs before running

- Add result controls before starting the simulation. For CFD, SimScale provides forces and moments, surface data, probe points, and field calculations. (source: sources/ca19.md)
- Use force and moment histories to monitor a rotating rotor, and use plots, planes, particle traces, and transient frames to inspect the flow. (source: sources/ca19.md, sources/ca24.md)
- Treat a visually plausible contour as inspection evidence, not as proof that the calculation is converged or mesh independent. > Inference: SimScale states that result controls help assess stabilization and that mesh quality influences stability and accuracy. (source: sources/ca19.md, sources/ca22.md)

See [[SimScale VAWT Transient Runs and Outputs]] and [[SimScale VAWT Results and Comparison]].

## 6. Learn by controlled comparison

- Start with a simple geometry and iterate; SimScale explicitly recommends a simple first problem to test whether an approach is viable. (source: sources/ca3.md)
- Change one design or operating variable at a time when comparing cases. > Inference: this is the minimum defensible comparison practice, but it is not specified as a SimScale requirement in the captured documentation. (source: sources/ca3.md, sources/ca19.md, sources/ca24.md)
- Compare meshes and monitor the same outputs across refinements before claiming a design improvement. SimScale recommends refining later for mesh-independence or convergence studies. (source: sources/ca21.md)

## What these sources do not establish

> Unverified: A specific VAWT rotor-domain size, mesh cell count, near-wall target, turbulence-model choice, MRF-versus-AMI selection rule, number of revolutions, torque-axis convention, or power-coefficient calculation procedure. The captured SimScale documentation describes available tools and broad setup guidance, not a validated VAWT case recipe. (source: sources/ca15.md, sources/ca21.md, sources/ca25.md, sources/ca26.md)

Related pages: [[CFD]], [[CFD and Validation]], [[cj1 CFD Modelling and Validation]].
