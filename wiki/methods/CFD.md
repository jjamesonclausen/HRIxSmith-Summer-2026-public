## Computational Fluid Dynamics (CFD)

Numerical method for simulating fluid flow by dividing the domain into discrete cells. (source: sources/n1.md, sources/va1.md)

![Figure 17: CFD Flow volume with stationary and rotating domains](../images/hri2526-fig17.jpg)

- Used to model wind flow and turbine performance. (source: sources/n1.md)
- Requires careful setup, boundary conditions, and mesh quality. (source: sources/n1.md)
- The HRI report used SimScale with stationary and rotating domains and a k-omega SST turbulence model. (source: sources/HRI2526.md)
- The workflow validated CFD against a NACA 0012 airfoil and a classical Savonius before analyzing the selected helical hybrid. (source: sources/HRI2526.md)
- The selected helical hybrid reported Cp 0.19 at TSR 1 in CFD. (source: sources/HRI2526.md)
- Used in a SolidWorks Flow Simulation study of a Savonius-Darrieus hybrid rotor with a 3D domain, mesh refinement, and nine attack angles from 0 to 120 degrees. (source: sources/vj2.md)
- A dynamic-stall study on a single-bladed 2D VAWT compared URANS, LES, and DES; DES matched PIV vorticity data best. (source: sources/vj5.md)
- That paper found grid refinement and convergence settings materially affected vorticity and force predictions. (source: sources/vj5.md)
- A later review organized VAWT CFD around problem definition, meshing, equation discretisation, boundary conditions, numerical solution, and post-processing. (source: sources/vj6.md)
- That review also emphasized static/dynamic meshing, turbulence-model choice, near-wall resolution, and experimental validation. (source: sources/vj6.md)
- It framed CFD as the detailed middle ground between lower-fidelity models and wind-tunnel experiments. (source: sources/vj6.md)
- The CRVAWT optimization paper used STAR-CCM+ CFD, validated an isolated VAWT against wind-tunnel data, and then used the simulation outputs in a response-surface optimization workflow. (source: sources/vj8.md)
