## Computational Fluid Dynamics (CFD)

Numerical method for simulating fluid flow by dividing the domain into discrete cells. (source: sources/n1.md, sources/va1.md)

![Figure 17: CFD Flow volume with stationary and rotating domains](../../images/hri2526-fig17.jpg)

- Used to model wind flow and turbine performance. (source: sources/n1.md)
- Requires careful setup, boundary conditions, and mesh quality. (source: sources/n1.md)
- The HRI report used SimScale with stationary and rotating domains and a k-omega SST turbulence model. (source: sources/HRI2526.md)
- The workflow validated CFD against a NACA 0012 airfoil and a classical Savonius before analyzing the selected helical hybrid. (source: sources/HRI2526.md)
- The selected helical hybrid reported Cp 0.19 at TSR 1 in CFD. (source: sources/HRI2526.md)
- The vj12 review treats CFD as the main way to study counter-rotation, blade-profile changes, deflectors, and site/layout effects when experiments are not practical. (source: sources/vj12.md)
- It says one deflector study used URANS with the k-omega turbulence model as the main analysis tool. (source: sources/vj12.md)
- It reinforces that CFD sits alongside field and lab testing for VAWT review work, not as a replacement for measurements. (source: sources/vj12.md)
- Used in a SolidWorks Flow Simulation study of a Savonius-Darrieus hybrid rotor with a 3D domain, mesh refinement, and nine attack angles from 0 to 120 degrees. (source: sources/vj2.md)
- A dynamic-stall study on a single-bladed 2D VAWT compared URANS, LES, and DES; DES matched PIV vorticity data best. (source: sources/vj5.md)
- That paper found grid refinement and convergence settings materially affected vorticity and force predictions. (source: sources/vj5.md)
- A later review organized VAWT CFD around problem definition, meshing, equation discretisation, boundary conditions, numerical solution, and post-processing. (source: sources/vj6.md)
- That review also emphasized static/dynamic meshing, turbulence-model choice, near-wall resolution, and experimental validation. (source: sources/vj6.md)
- It framed CFD as the detailed middle ground between lower-fidelity models and wind-tunnel experiments. (source: sources/vj6.md)
- The helical-VAWT study used 2D LES for blade-scale flow and 3D U-RANS with SST k-omega for the full rotor. (source: sources/va4.md)
- It found that 3D effects such as tip vortex and second flow reduce performance relative to 2D predictions. (source: sources/va4.md)
- A helical-VAWT helix-angle study used Ansys FLUENT with stationary and rotating domains, a sliding mesh interface, transition SST k-omega turbulence modeling, grid/time-step independence checks, and validation against McLaren's experimental VAWT data. (source: sources/va7.md)
- That study used z-vorticity contours and wake profiles to connect section-wise blade loading, vortex shedding, wake interaction, and flow separation to moment-coefficient behavior. (source: sources/va7.md)

## Figures

![Figure 11: streamlines showing wake-vortex interaction](../../images/va4-fig11.jpg)
![Figure 14: 2D LES versus 3D U-RANS power coefficient](../../images/va4-fig14.jpg)
![Figure 2: stationary and rotating CFD domains](../../images/va7-fig2.jpg)
![Figure 21: z-vorticity at different TSRs](../../images/va7-fig21.jpg)
- The CRVAWT optimization paper used STAR-CCM+ CFD, validated an isolated VAWT against wind-tunnel data, and then used the simulation outputs in a response-surface optimization workflow. (source: sources/vj8.md)

![Figure 21: Schematic view and CFD streamlines for flow around a flanged diffuser](../../images/vj12-fig21.jpg)

#methods
