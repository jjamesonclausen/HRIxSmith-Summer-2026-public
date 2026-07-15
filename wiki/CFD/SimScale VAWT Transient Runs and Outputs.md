---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[ca6]]"
  - "[[ca8]]"
  - "[[ca16]]"
  - "[[ca17]]"
  - "[[ca18]]"
  - "[[ca19]]"
Source_count: 6
tags:
  - cfd
---
# SimScale VAWT Transient Runs and Outputs

## Time dependency and solver control

Use transient analysis when the time-dependent solution is the object of study; SimScale describes steady-state simulations as less computationally demanding and applicable when only a converged steady solution is needed. (source: sources/ca8.md)

In a transient run, end time is the simulated duration and `Delta t` is the time-step size. (source: sources/ca18.md)

Enable adjustable time step to let SimScale change `Delta t` based on the maximum Courant number and maximum allowed time step. (source: sources/ca18.md)

The Courant relation is `C = U Delta t / Delta x`; SimScale recommends CFL below `1` for explicit schemes and says `0.5-0.7` often gives the best results. (source: sources/ca18.md)

> Unverified: The correct timestep for a VAWT. It depends on local velocity and cell length through CFL, but the captured documentation does not prescribe angular resolution, steps per revolution, or the number of rotor revolutions to simulate. (source: sources/ca18.md, sources/ca32.md)

## Numerical settings

Keep numerical settings at their defaults unless a specific need is identified; SimScale documents its numerical controls as advanced-user settings and advises defaults unless necessary. (source: sources/ca6.md)

If initial time-step stability or convergence is problematic, potential-flow initialization can provide better initial conditions by solving a pressure equation from velocity initial and boundary conditions. (source: sources/ca18.md)

## Output plan

Configure result controls before the run. In CFD these include forces and moments, surface data, probe points, and field calculations such as vorticity, pressure coefficient, turbulence fields, and wall shear stress. (source: sources/ca19.md)

For a VAWT case, create force and moment controls on the rotor surfaces and decide in advance which probes and planes will diagnose the wake. > Inference: forces and moments are calculated on selected surfaces, and probes measure selected flow variables; the VAWT-specific selection is a study-design decision. (source: sources/ca19.md)

Choose write control and interval deliberately. SimScale can write by timestep, clock time, runtime, CPU time, or adjustable runtime; excessive writes increase result data while sparse writes can miss time-resolved behavior. The first statement is documented and the tradeoff is an inference from the documented write-frequency controls. (source: sources/ca18.md)

## Convergence review

Result-control histories can be used to assess whether iterative variables stabilize and to stop a simulation that is not progressing as intended. (source: sources/ca19.md)

For transient cases, do not declare convergence solely from residuals. > Inference: residuals assess solution behavior within the numerical solve, while the design-relevant forces and moments must also show an adequately repeatable behavior over the period chosen for analysis. (source: sources/ca18.md, sources/ca19.md)

Related pages: [[SimScale VAWT CFD Learning Path]], [[SimScale VAWT Results and Comparison]], [[SimScale VAWT Mesh and Quality]].
