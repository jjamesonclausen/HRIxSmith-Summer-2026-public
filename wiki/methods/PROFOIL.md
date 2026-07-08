---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[vj24]]
Source_count: 1
Tags: #methods
---
## PROFOIL

Interactive multipoint inverse-airfoil-design code used in `vj24` as the core tool for tailoring a low-Re symmetric airfoil for a straight-bladed Darrieus VAWT. (source: sources/vj24.md)

- The method starts from desired velocity-distribution behavior rather than only testing predefined airfoil geometries. (source: sources/vj24.md)
- It divides the circle/airfoil mapping into segments so different parts of the airfoil can be prescribed for different design operating conditions. (source: sources/vj24.md)
- The source says practical solutions must satisfy continuity, closure, and far-field constraints, with additional iterative constraints such as thickness and pitching moment. (source: sources/vj24.md)
- In `vj24`, PROFOIL is coupled with `XFOIL` for airfoil analysis and `CARDAAV` for rotor-performance prediction, and the combined workflow is iterated until the VAWT meets a `10-15%` power-improvement target at `TSR = 1.6`. (source: sources/vj24.md)
- The paper says the strength of the approach is the inverse-design logic itself, while the main weakness is still the low-Re/high-angle-of-attack aerodynamic analysis used to judge the result. (source: sources/vj24.md)

![Source figure](vj24-fig1.jpg)
Original caption: Figure 1: The inverse airfoil design strategy as employed for improved performance of a VAWT. [[vj24|Source]]

Related: [[Double-Multiple Streamtube Model]], [[Panel Method]], [[Straight-bladed Darrieus]], [[vj24-summary]]

#methods
