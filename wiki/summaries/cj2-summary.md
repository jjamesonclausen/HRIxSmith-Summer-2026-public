---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj2]]"
Source_count: 1
tags:
  - summaries
---
## cj2 Summary

This paper uses 3D transient Fluent CFD to assess a 12-blade Farrah VAWT against prior wind-tunnel data for positive and negative pitch angles of 7, 15, 20, and 40 degrees. (source: sources/cj2.md)

- The chosen method is pressure-based transient RANS with `k-omega SST`, sliding mesh, a matching rotating/stationary interface, second-order schemes, `SIMPLEC`, and a 0.3-degree angular step. (source: sources/cj2.md)
- A fine 14,438,984-cell unstructured mesh with `y+ = 1` produced 4.77 W when the 12 airfoils were defined as separate walls, versus 4.97 W experimental power in the grid comparison. (source: sources/cj2.md)
- The authors reject Spalart-Allmaras for this case because it did not reproduce a sinusoidal torque signal and its best reported fine-grid error was 43.25%. (source: sources/cj2.md)
- The paper reports comparable power trends, not an unadjusted direct match: the CFD-versus-test comparison assumes either 50% or 20% mechanical losses. (source: sources/cj2.md)
- It reports wake recovery at 9D and a near-wake recirculation region to about 2.6D for the studied cases. (source: sources/cj2.md)

![Figure 6: Grid-resolution comparison.](../../attachments/images/cj2-fig6.jpg)
Original caption: Figure 6. Volume ratio contours of grid generated: (a) coarse; (b) medium; (c) fine. [[cj2|Source]]

> Uncertainty: the study models half the turbine with symmetry and then adjusts the CFD comparison using assumed mechanical losses. Its evidence supports the selected CFD setup and trends for this Farrah turbine, but does not establish an unadjusted absolute-power prediction for other VAWTs. (source: sources/cj2.md)

Related pages: [[CFD]], [[CFD and Validation]], [[cj2 Farrah VAWT CFD Setup]]

#summaries
