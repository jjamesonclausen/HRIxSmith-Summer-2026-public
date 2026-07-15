---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[ca19]]"
  - "[[ca23]]"
  - "[[ca24]]"
  - "[[cj7]]"
Source_count: 4
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

The sources establish that SimScale can calculate forces and moments, but they do not state a VAWT torque-axis convention or a procedure to turn an exported moment into shaft power or `Cp`. (source: sources/ca19.md)

> Unverified: Any power or coefficient calculation based on SimScale output must define the moment component, sign convention, angular speed, reference area, and averaging interval before it can support a VAWT design claim.

Related pages: [[SimScale VAWT Transient Runs and Outputs]], [[SimScale VAWT CFD Learning Path]], [[CFD and Validation]].
