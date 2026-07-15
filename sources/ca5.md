---
title: "ca5"
source: "https://www.simscale.com/docs/analysis-types/"
author:
published: 2018-10-30
created: 2026-07-15
description: "The SimScale Workbench is a single interface that supports a variety of simulation types. Find out which analysis types are supported."
tags:
  - "clippings"
---
Documentation

## Analysis Types

As the next step in any [new simulation setup](https://www.simscale.com/docs/simulation-setup/), once the [geometry is free from all faults](https://www.simscale.com/docs/cad-preparation/#cad-faults) and ready for simulation, the analysis type that best fits the simulation case needs to be selected. A list of all the supported analysis types is listed in the figure below:

![list of all analysis types supported in simscale](https://frontend-assets.simscale.com/media/2025/07/image-13.png)

Figure 1: List of all the available analysis types in SimScale. Click on the desired analysis type or click on ‘Need Help?’ to receive help choosing one.

Subscription Plans

Community users will not have access to all the analysis types. Analysis types with the ‘SPECIAL’ tag require additional subscription plans. Checkout our [pricing page](https://www.simscale.com/product/pricing/).

![special tag analysis types simscale](https://frontend-assets.simscale.com/media/2025/07/image-14.png)

Figure 2: List of analysis types with the ‘SPECIAL’ tag. Community users will not have access to these

The list is segregated based on flow, and structural mechanics. Select the desired type and hit the **‘Create Simulation’** button. This leads to the SimScale Workbench.

Need Help?

If you need help selecting the appropriate analysis type for your model click on **‘Need Help?’** Answer a set of simple questions that will help you choose the most relevant analysis type.

In the following the currently supported analysis types and their basic use cases are described:

## Fluid Dynamics (OpenFOAM®)

The following types can be used to simulate fluid flow and are based on the [OpenFOAM **®**](https://openfoam.org/) solver:

- **[Incompressible](https://www.simscale.com/docs/analysis-types/incompressible-fluid-flow-analysis/)**: This analysis type is used to run CFD simulations in which fluid density variations are negligible. This assumption is typically valid when velocities and temperature gradients are small.
- **[Compressible](https://www.simscale.com/docs/analysis-types/compressible-fluid-flow-analysis/)** ****(Special* Feature)***: This analysis type is used to run CFD simulations where density variations have a significant influence on the system. This commonly occurs when the flow velocities exceed ~30% of the speed of sound.
- **[Convective Heat Transfer](https://www.simscale.com/docs/analysis-types/convective-heat-transfer-analysis/)**: This analysis type is used when the temperature changes in the fluid lead to density variations and movement of the fluid due to gravity. This solver is commonly used for natural convection but can also be used for forced convection when flow motion is induced by external forces. Radiative heat transfer can also be modeled.
- [**Conjugate Heat Transfer (CHT)**](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/): Also referred to as CHT, this analysis type is used to simulate heat transfer within and between solid and fluid domains by exchanging thermal energy at the interfaces between them. Electronic enclosures and heat exchangers are some of the common applications for CHT simulation.
- **[Conjugate Heat Transfer (IBM)](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-ibm/)**:The Immersed Boundary analysis type (IBM) is identical to the CHT analyses types however its meshing is based on a cartesian grid where the geometry gets immersed into. IBM is resilient to complex geometrical details and does not require CAD simplification.
- **[Multiphase](https://www.simscale.com/docs/analysis-types/multiphase-fluid-flow-analysis/) **(Special* Feature)***: This analysis type is used to simulate the time-dependent behavior of two-fluid mixture, for example, air and water. The analysis is carried out using the VoF (Volume of Fluid) method.

*Special Feature*

*Compressible, Multiphase, Multi-purpose, Incompressible (LBM), and Pedestrian Wind Comfort* analysis types will only be accessible to users with a Professional plan and those who are already on the Community plan. New Community users or those recently downgraded to the Community plan will no longer be able to perform simulations with these 3 analysis types. See our [pricing page](https://www.simscale.com/product/pricing/) to request additional features.

Which simulation type is appropriate for you?

If you liked reading this document you will enjoy watching a video on how to appropriately choose an analysis or simulation type based on the given geometry or the outcome expected.

![](https://www.youtube.com/watch?v=qO1wPV4qXmU)

## Fluid Dynamics (LBM solver)

- **[Incompressible (LBM)](https://www.simscale.com/docs/analysis-types/incompressible-lbm/) *(Special Feature)***: This analysis type is used to simulate the transient effects of external flow around objects using the Lattice Boltzmann method (LBM). It assumes that fluid density variations are negligible, which is typically valid when velocities and temperature gradients are small. It is capable of simulating large transient flow simulations.
- [**Pedestrian Wind Comfort**](https://www.simscale.com/docs/analysis-types/pedestrian-wind-comfort-analysis/) ***(Special Feature)***: This analysis type is used to simulate transient wind analysis over large regions (cities, parks, etc.) with up to 36 wind directions. It is useful to compute wind comfort and safety of the pedestrians in accordance with the wind engineering standards.  
	The analysis type uses LBM and, therefore, assumes that fluid density variations are negligible, which is typically valid when velocities and temperature gradients are small.

Note

The above analysis types with LBM solver are available only to our users with the [Professional Plan](https://www.simscale.com/product/pricing/).

## Fluid Dynamics (Multi-purpose)

- [**Multi-purpose**](https://www.simscale.com/docs/analysis-types/subsonic-cartesian/) ****(Special* Feature)***: This analysis provides the possibility to simulate both incompressible and compressible, laminar or turbulent flows in a single framework. It offers a robust binary-tree based meshing strategy producing a body-fitted Cartesian mesh suitable for accurate Finite Volume discretization used by the underlying solver. The analysis type covers a wide range of flow speeds and offers faster runtimes and convergence compared to the industry standards.

## Solid Mechanics (Code\_Aster)

The following simulation types for structural mechanics and finite element analysis are based on the [Code\_Aster](https://www.code-aster.org/) solver:

- **[Static](https://www.simscale.com/docs/analysis-types/static/)**: This analysis type is used to determine the displacements and stresses in structures or components caused by the applied constraints and steady loads while ignoring inertia and damping effects. Static analysis can be either linear or nonlinear.
- **[Dynamic](https://www.simscale.com/docs/analysis-types/dynamic/)**: This analysis type enables the time-dependent calculation of displacements and stresses in one or more solid bodies. If the rate of application of the load is important, then a dynamic analysis should be used, otherwise, a static analysis might be sufficient.
- **[Heat Transfer](https://www.simscale.com/docs/analysis-types/heat-transfer/)**: This analysis type is used to determine the temperature distribution and heat flux in a solid body. Both linear and non-linear material behaviors are supported.
- **[Thermomechanical](https://www.simscale.com/docs/analysis-types/thermomechanical/)**: This analysis type is used to determine the structural and thermal stress in a solid body subjected to thermal and structural loads.
- **[Frequency Analysis](https://www.simscale.com/docs/analysis-types/frequency-analysis/)**: This analysis type is used to calculate the natural frequencies of constrained or free parts and assemblies. Besides the numerical value of the eigenfrequencies, the results provide insights into the deformation behavior of the corresponding eigenmodes.
- [**Harmonic**](https://www.simscale.com/docs/analysis-types/harmonic/): This analysis type is used to determine the response of a structure under steady-state periodic (sinusoidal) loading at a given range of frequencies including the effects of material damping.

## Solid Mechanics (MARCTM)

- **[Nonlinear Mechanical (Marc):](https://www.simscale.com/docs/analysis-types/nonlinear-mechanical/)** The Nonlinear Mechanical (Marc) analysis type is used to simulate intricate mechanical responses in structural elements and components subjected to significant deformation, challenging contact interactions—including self-contact—and strongly nonlinear material behaviors.

## Electromagnetics

The [Electromagnetics (EM)](https://www.simscale.com/docs/analysis-types/electromagnetics/) solver is aimed at providing a powerful tool for simulating electromagnetic phenomena in the cloud. SimScale’s focus is centered around low-frequency domains, which include a major part of electromagnetic devices. Parameters such as magnetic flux density, magnetic field strength, current density, nonlinear materials, permanent magnets, inductances, etc. can be investigated.

Last updated: October 9th, 2025

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries