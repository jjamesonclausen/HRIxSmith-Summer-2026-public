---
Created: 2026-07-16
Updated: 2026-07-17
Sources:
  - "[[fa1]]"
Source_count: 1
tags:
  - concepts
---
# Finite Wing Aerodynamics

A finite wing has physical spanwise ends, so its aerodynamic behavior differs from that of a two-dimensional airfoil section. (source: sources/fa1.md)

- The pressure difference between a lifting wing's lower and upper surfaces drives flow around each wingtip, forming trailing tip vortices. (source: sources/fa1.md)
- The vortices induce downwash, reducing local effective angle of attack and lift relative to the two-dimensional airfoil value. (source: sources/fa1.md)
- The rearward tilt of the lift vector adds induced drag. (source: sources/fa1.md)
- The source defines wing aspect ratio as `AR = span^2 / planform area`; a larger aspect ratio reduces the influence of tip vortices over most of the wing. (source: sources/fa1.md)
- Finite-wing lift and drag coefficients use planform area as the reference area, not wetted surface area. (source: sources/fa1.md)

## Preliminary relations

For an ideally elliptically loaded wing, the induced angle of attack and induced-drag coefficient are `alpha_i = C_L / (pi AR)` and `C_Di = C_L^2 / (pi AR)`, respectively. (source: sources/fa1.md)

For a non-elliptical spanwise lift distribution, the source gives `C_Di = (1 + delta) C_L^2 / (pi AR)`, where `delta >= 0` is a span-loading correction factor; elliptical loading has `delta = 0` and gives the minimum induced drag for specified lift, span, and dynamic pressure. (source: sources/fa1.md)

> Inference: these finite-wing relations provide a first reminder that VAWT blade tips produce three-dimensional losses, but they are not a complete VAWT performance model. A rotating VAWT blade has time-varying relative flow, dynamic stall, and blade-wake interaction that this fixed-wing treatment does not represent.

## Airfoil-validation implication

> Inference: a finite-span CFD model with exposed tips must not be validated against a two-dimensional airfoil polar. To validate against a sectional polar, use a truly 2D analysis or a spanwise-extruded pseudo-2D model that eliminates exposed tips. (source: sources/fa1.md)

Related pages: [[CFD and Validation]], [[ca33 ANSYS Airfoil Validation Workflow]], [[Airfoil Selection for Small Straight-Bladed VAWTs]].

#concepts
