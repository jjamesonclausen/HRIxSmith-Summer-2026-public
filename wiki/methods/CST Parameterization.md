---
Created: 2026-06-26
Updated: 2026-07-07
Sources:
  - "[[va2]]"
  - "[[vj17]]"
Source_count: 2
tags:
  - methods
---
## CST Parameterization

Class/Shape Transformation (CST) is a geometry representation method for defining airfoil profiles with a compact set of coefficients. (source: sources/va2.md)

![Source figure](va2-fig9.jpg)
Original caption: Figure 9: NACA0015 airfoil expressed by CST function [[va2|Source]]

- The class function is written as `C(x) = k x^N1 (1-x)^N2`. (source: sources/va2.md)
- The shape function uses Bernstein polynomials. (source: sources/va2.md)
- The paper uses CST to reconstruct NACA0015 and defines 13 geometric variables before screening to 7 design variables. (source: sources/va2.md)
- Leading-edge radius, thickness, and trailing-edge thickness are controlled through selected coefficients. (source: sources/va2.md)
- The vj17 study uses CST as the airfoil-shape generator for a Savonius optimization problem and treats the CST coefficients as the decision variables. (source: sources/vj17.md)
- It optimizes the airfoil using eight curvature variables after fixing the first coefficients. (source: sources/vj17.md)

Related: [[H-VAWT]], [[Kriging Surrogate Model]], [[Multi-Island Genetic Algorithm]]

#methods
