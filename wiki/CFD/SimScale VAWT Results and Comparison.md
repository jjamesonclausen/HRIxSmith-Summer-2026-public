---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[HRI2526]]"
  - "[[ca19]]"
  - "[[ca23]]"
  - "[[ca24]]"
  - "[[cj7]]"
Source_count: 5
tags:
  - cfd
---
# SimScale VAWT Results and Comparison

## Open and inspect results

After results are available, open the online post-processor with **Post-process results** or **Solution Fields**. (source: sources/ca24.md)

The `cj7` tutorial adds a rotating-machinery inspection sequence: move to the last timestep, clear predefined filters, hide enclosure walls, and color the rotating geometry by pressure before adding streamline-style filters. (source: sources/cj7.md)

For a transient run, use the frame-selection toolbox to move through saved result sets. (source: sources/ca24.md)

## Minimum evidence package

- Plot the forces and moments configured before the run; SimScale calculates them on assigned surfaces. (source: sources/ca19.md)
- Use cutting planes and velocity vectors to inspect flow structure at consistent locations. (source: sources/ca24.md)
- Use particle traces from a seed face to inspect recirculation and flow patterns. (source: sources/ca24.md)
- In the `cj7` example, particle traces are seeded below the rotor system and configured more densely to reveal the swirl passing through the rotating region. (source: sources/cj7.md)
- Use the rotational filter to inspect a rotating region, including blade-to-blade and unwrapped cascade views. (source: sources/ca24.md)
- The same tutorial also uses a cutting plane with vectors through the rotating region to inspect local acceleration and swirl direction. (source: sources/cj7.md)
- Save a consistent view for repeated comparisons across simulations. SimScale's Save view stores views and filters for use across runs and projects. (source: sources/ca24.md)

## Compare designs fairly

SimScale's Compare tool shows two runs side by side using synchronized views and filters, but both views show their latest timestep only. (source: sources/ca24.md)

> Inference: Use Compare for visual inspection, but compare time histories and selected equivalent time states separately for transient VAWT cases. The latest-timestep limitation makes a single Compare view insufficient evidence for periodic rotor performance. (source: sources/ca24.md)

## Quantities not yet established

For a VAWT `Cp` estimate, configure a **Forces and moments** result control on the rotor surfaces and extract the moment component about the rotor shaft axis. SimScale establishes that this control calculates forces and moments on selected surfaces; `HRI2526` reports using the total moment about its VAWT's centered Z-axis. (source: sources/ca19.md, sources/HRI2526.md)

`HRI2526` reports a moment coefficient of about `0.3` for its validated Classical Savonius case at TSR `0.8`, then calculates `Cp` as moment coefficient multiplied by TSR: `Cp = Cm * TSR`. This is a project-specific reported calculation, not a general SimScale result-control setting. (source: sources/HRI2526.md)

For a transient rotor, use the moment history to select a repeatable period and average the chosen moment or moment coefficient before making a performance claim. > Inference: SimScale allows force and moment histories to assess stabilization, while HRI reports an oscillating torque coefficient with a mean value. (source: sources/ca19.md, sources/HRI2526.md)

The VAWT review in `vj6` defines torque coefficient as:

$$
C_t = \frac{T}{0.5\rho A R V_\infty^2}
$$

where `T` is mean shaft torque, `rho` is air density, `A` is reference area (typically swept area `D * H`), `R` is rotor radius, and `V_infinity` is free-stream wind speed. It then gives `Cp = Ct * TSR`. (source: sources/vj6.md)

Use one normalization convention consistently. `vj6` warns that `Cm` can be used interchangeably with `Ct` or can instead denote a moment coefficient referenced to chord length. (source: sources/vj6.md)

Use probe points, field calculations such as vorticity or pressure coefficient, cutting planes, and particle traces to diagnose the flow that produces the torque; these controls and visualizations do not directly calculate VAWT `Cp`. (source: sources/ca19.md, sources/ca24.md)

> Uncertainty: The captured SimScale documentation does not provide a built-in VAWT `Cp` result control or a standard torque-axis/sign convention. Define the selected rotor surfaces, shaft axis, sign convention, TSR, reference area, and averaging interval before treating a calculated `Cp` as a design result. (source: sources/ca19.md, sources/HRI2526.md)

Related pages: [[SimScale VAWT Transient Runs and Outputs]], [[SimScale VAWT CFD Learning Path]], [[CFD and Validation]].
