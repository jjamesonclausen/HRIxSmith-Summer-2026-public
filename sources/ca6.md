---
title: "ca6"
source: "https://www.simscale.com/docs/analysis-types/incompressible-fluid-flow-analysis/"
author:
published: 2018-11-24
created: 2026-07-15
description: "Incompressible fluid flow analysis is for simulations in which fluid density variations are negligible. Learn about the analysis now!"
tags:
  - "clippings"
---
Documentation

## Incompressible Fluid Flow Analysis

The **Incompressible** fluid flow analysis is used to run [fluid simulations](https://www.simscale.com/product/cfd/) where density variations are negligible. This assumption is typically valid when velocities and temperature gradients are small.

Mathematically speaking, the divergence of the flow velocity ($u$) is zero:

$$
\nabla . u = 0
$$

![incompressible analysis over burj al arab in simscale](https://frontend-assets.simscale.com/media/2020/08/incompressible-simulation.jpg)

Figure 1: Incompressible aerodynamics simulation over ‘Burj-Al-Arab’ with velocity streamlines and turbulent viscosity contours

Within SimScale, one can effortlessly set up an incompressible simulation with the steps described below.

## Creating an Incompressible Analysis

To create an incompressible analysis, first, select the desired geometry and click on **‘Create Simulation’**:

![create simulation drone simulation mrf rotating zone](https://frontend-assets.simscale.com/media/2024/12/image-56.png)

Figure 2: Steps to create a simulation in SimScale

Next, a window with a list of several analysis types supported in SimScale will be displayed:

![incompressible analysis type](https://frontend-assets.simscale.com/media/2025/07/image-15.png)

Figure 3: Select the ‘Incompressible’ analysis type from the tree above and click on ‘Create Simulation’ at the bottom.

Choose the **‘Incompressible’** analysis type and click on **‘Create Simulation’**. This will lead to the workbench for the incompressible flow simulation with the following simulation tree and the respective settings:

![list of items in incompressible analysis](https://frontend-assets.simscale.com/media/2020/08/incompressible-list.png)

Figure 4: Simulation tree for incompressible analysis in SimScale Workbench

## Global Settings

To access the global settings, click on ‘ **Incompressible** ‘ in the simulation tree. It consists of certain parameters that can be selected to define the [fluid simulation](https://www.simscale.com/product/cfd/). The parameters are listed below:

- *Turbulence model*
- *Time dependency*: *Steady state* or *Transient*
- *Algorithm*
- *Passive species*

For detailed information about each of these parameters, visit the [global settings](https://www.simscale.com/docs/simulation-setup/global-settings/) page.

## Geometry

The *Geometry* section allows you to view and select the CAD model required for the simulation. It is important that the CAD model is well prepared to avoid any meshing or simulation related errors. Find more details on CAD preparation and upload [here](https://www.simscale.com/docs/cad-preparation/).

## Model

This section only appears if an LES (large eddy simulation) turbulence model is chosen inside global settings. Here, parameters related to the delta coefficient in LES need to be specified.

Find further information about the model section [here](https://www.simscale.com/docs/simulation-setup/model/).

## Materials

Here, the appropriate fluid for the simulation can be specified. The user has the freedom to select the fluid properties based on the chosen *Viscosity model.* For more information, please visit the relevant documentation page for [materials](https://www.simscale.com/docs/simulation-setup/materials/).

## Initial Conditions

In an incompressible simulation, the computational domain will be solved for two fields: pressure $\left(P\right)$ and velocity $\left(U\right)$. Additional turbulent transport quantities may be included based on the turbulence model selected. Under *Initial conditions*, these values can be initialized for the whole domain or a sub-domain.

Important

For any simulation, initial and boundary conditions must be specified for all required variables on every boundary.

It is recommended to set the **initial conditions** close to the expected solution to avoid potential convergence problems. Alternatively, SimScale provides the possibility to use a potential flow solver to initialize the field before starting the actual simulation. This option is available under [Simulation Control](https://www.simscale.com/docs/simulation-setup/simulation-control/).

Learn how the initialization process takes place in depth in this [document](https://www.simscale.com/docs/simulation-setup/initial-conditions/).

## Boundary Conditions

Boundary conditions help to add closure to the problem in hand by defining how a system interacts with the environment. Check out this [detailed list](https://www.simscale.com/docs/simulation-setup/boundary-conditions/) of available boundary conditions and how they can be applied to the domain boundaries.

Some boundary conditions available in incompressible simulations are supported in parametric experiments. Learn more details in [this article](https://www.simscale.com/knowledge-base/how-to-run-parametric-studies-in-simscale/).

Important

In case no boundary conditions are assigned to a face, by default it will receive a no-slip [wall boundary condition](https://www.simscale.com/docs/simulation-setup/boundary-conditions/wall/) with wall function for turbulence resolution.

## Advanced Concepts

Under *Advanced concepts*, you will find additional setup options, such as *Rotating zones, Momentum sources, Porous media, Solid body motions, and Passive scalar sources*. Visit this dedicated [page](https://www.simscale.com/docs/simulation-setup/advanced-concepts/) for more information.

Furthermore, momentum sources and rotating zones are supported in parametric experiments. Please visit [this article](https://www.simscale.com/knowledge-base/how-to-run-parametric-studies-in-simscale/) for more details.

## Numerics

Numerical settings play an important role in the simulation configuration. They define how to solve the equations by applying proper discretization schemes and solvers to the equations. They help enhance the stability and robustness of the simulation. Although all numerical settings are made available for users to have full control over, it is advised to keep them default unless necessary.

Note

SimScale uses its own version of [OpenFOAM®](https://www.openfoam.com/) solvers developed in-house.

Numerical settings are recommended for advanced users but interested readers are encouraged to learn more about them through [this documentation](https://www.simscale.com/docs/simulation-setup/numerics/).

## Simulation Control

The *Simulation control* settings define the general controls over the simulation. In this tab, a series of variables can be set. For example, the *End time* and *Maximum runtime* for the simulation can be defined.

For a complete overview of the parameters and their meaning, check this [page](https://www.simscale.com/docs/simulation-setup/simulation-control/).

## Result Control

The *Result Control* section allows users to define additional simulation result outputs. It controls how the results will be written meaning the write frequency, location, statistics of the output data, etc.

Find more details about result controls [here](https://www.simscale.com/docs/simulation-setup/result-control/).

## Mesh

[Meshing](https://www.simscale.com/docs/simwiki/preprocessing/what-is-a-mesh/) is the process of discretization of the simulation domain. That means we split up a large domain into multiple smaller domains and solve equations for them.

For an incompressible analysis, the [standard](https://www.simscale.com/docs/simulation-setup/meshing/standard/), [hex-dominant](https://www.simscale.com/docs/simulation-setup/meshing/hex-dominant/), and [hex-dominant parametric](https://www.simscale.com/docs/simulation-setup/meshing/hex-dominant/#advanced-settings-parametric) algorithms are available. To learn more about the mesh settings in SimScale and its upload, visit [this page](https://www.simscale.com/docs/simulation-setup/meshing/).

## Related Tutorials

SimScale offers a large number of tutorials on incompressible fluid flow each with a different purpose. Interested? Quickly check out [our page](https://www.simscale.com/docs/tutorials/) for all the basic and advanced tutorials.

Last updated: April 15th, 2026

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries