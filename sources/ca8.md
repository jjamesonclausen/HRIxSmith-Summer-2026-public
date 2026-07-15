---
title: "ca8"
source: "https://www.simscale.com/docs/simulation-setup/global-settings/"
author:
published: 2019-06-11
created: 2026-07-15
description: "Settings like the turbulence model, time dependency, and material behavior can ge defined as part of the global settings of a simulation."
tags:
  - "clippings"
---
Documentation

## Global Settings

Settings like the turbulence model, time dependency, and material behavior can be defined as part of the **Global Settings** of a simulation. The global settings of a simulation are accessed by clicking on the first entry of a simulation tree:

![global simulation settings for an incompressible analysis on simscale](https://frontend-assets.simscale.com/media/2025/05/image-4.png)

Figure 1: The global simulation settings define the physics of the simulation setup.

In this documentation page, we will go through the parameters that are defined in the global settings. For convenience, these parameters will be divided into two main categories: Computational Fluid Dynamics (CFD) and Finite Element Analysis (FEA).

## Computational Fluid Dynamics

Turbulence modeling is an important issue in many CFD simulations. Virtually, all engineering applications are turbulent and hence require a turbulence model. When turbulence is present, it usually dominates all other flow phenomena, which results in energy dissipation, mixing, heat transfer, and drag being increased $$. Turbulence modeling is the construction and use of a model to predict the effects of turbulence.

The common turbulence models used in CFD applications are RANS-based models, especially two-equation models. SimScale makes available some of the most commonly used models in industrial and research applications. In a *Laminar* flow, associated with low Reynolds numbers, viscous effects dominate the flow and turbulence can be neglected. This flow regime is characterized by regular flow layers.

Currently, the following models are supported:

- [K-epsilon](https://www.simscale.com/docs/simulation-setup/global-settings/k-epsilon/#standard-k-epsilon-model)
- [Realizable K-epsilon](https://www.simscale.com/docs/simulation-setup/global-settings/k-epsilon/#realizable-k-epsilon-model)
- [K-omega](https://www.simscale.com/docs/simulation-setup/global-settings/k-omega-sst/#standard-k-omega-model)
- [K-omega SST](https://www.simscale.com/docs/simulation-setup/global-settings/k-omega-sst/#k-omega-sst)
- [LES Smagorinsky](https://www.simscale.com/docs/simulation-setup/global-settings/les-turbulence-models/#les-smagorinsky-model)
- [LES Spalart-Allmaras](https://www.simscale.com/docs/simulation-setup/global-settings/les-turbulence-models/#les-spalart-allmaras-model)
- [LES Smagorinsky (Direct)](https://www.simscale.com/docs/simulation-setup/global-settings/les-turbulence-models/#les-smagorinsky-direct-model): only available for the [Incompressible (LBM)](https://www.simscale.com/docs/incompressible-lbm-lattice-boltzmann-advanced/) solver
- [K-omega SST (DDES)](https://www.simscale.com/docs/incompressible-lbm-lattice-boltzmann-advanced/#des-models): only available for the [Incompressible (LBM)](https://www.simscale.com/docs/incompressible-lbm-lattice-boltzmann-advanced/) solver
- [K-omega SST (IDDES)](https://www.simscale.com/docs/incompressible-lbm-lattice-boltzmann-advanced/#des-models): only available for the [Incompressible (LBM)](https://www.simscale.com/docs/incompressible-lbm-lattice-boltzmann-advanced/) solver

For further information on turbulence, please visit this SimWiki [article](https://www.simscale.com/docs/simwiki/cfd-computational-fluid-dynamics/what-is-turbulent-flow/).

There are two variants of simulation: *Steady-state* and *Transient*. To account for time-dependent effects, consider a transient simulation. If you are only interested in the converged steady-state solution, consider a steady-state simulation. Steady-state simulations are computationally less demanding.

Note

In the case of a multiphase analysis, the time dependency setting will always be set to transient.

In SimScale, the following algorithms are available:

- For steady-state analysis: *SIMPLE*;
- For transient analysis with turbulence: *PISO*, *PIMPLE*;
- Lastly, for transient laminar analysis: *ICO*.

These algorithms are responsible for the pressure-velocity coupling. For additional information, readers are referred to this [page](https://cfd.direct/openfoam/user-guide/v7-fvsolution/) $$.

Passive scalar transport is available for [incompressible](https://www.simscale.com/docs/analysis-types/incompressible-fluid-flow-analysis/) and [convective heat transfer](https://www.simscale.com/docs/analysis-types/convective-heat-transfer-analysis/) analysis.

Passive scalars allow you to simulate the transport of a scalar quantity within a fluid flow. The core assumption of this is that the species that is transported within the flow does not affect the fluid flow (therefore passive).

This is a valid assumption, for example, for the transport of oxygen within a water flow. It is important to note that scalar transport does not assume any physical dimensions for passive quantities.

<iframe title="“Passive Scalar Sources” — SimScale" src="https://www.simscale.com/docs/simulation-setup/advanced-concepts/passive-scalar-sources/embed/#?secret=dxNruXVkqn#?secret=mOoPK4wS3r" width="500" height="340" frameborder="0"></iframe>

This parameter is exclusive to [convective heat transfer](https://www.simscale.com/docs/analysis-types/convective-heat-transfer-analysis/), [conjugate heat transfer](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/), [conjugate heat transfer (IBM)](https://www.simscale.com/docs/analysis-types/immersed-boundary-analysis/), and [multi-purpose](https://www.simscale.com/docs/analysis-types/subsonic-cartesian/) analyses. The user can enable or disable this parameter via an on/off toggle.

When the toggle is off, the Boussinesq approximation is used. This approximation is valid for small temperature variations within the domain. This assumption is often used, for example, in natural convection simulations. If the toggle is off, use *Gauge pressure (0 $P a$)*.

When *Compressible* is toggled on, the resulting density variations within the domain are calculated based on pressure and temperature. If the toggle is on, use Absolute pressure (as an example 101325 $P a$ at sea level).

Heat transfer through radiation takes place in the form of electromagnetic waves and it can be calculated in the simulation. This phenomenon becomes more important when the temperatures involved in the simulation are large.

Both convective and conjugate heat transfer analysis types support radiation.

<iframe title="“Radiation Behaviour for Convective &amp; Conjugate Heat Transfer Simulations” — SimScale" src="https://www.simscale.com/docs/analysis-types/convective-heat-transfer-analysis/radiation/embed/#?secret=bzcqXI9MKM#?secret=a8jDKbvd5l" width="500" height="369" frameborder="0"></iframe>

This setting is exclusive to [multiphase](https://www.simscale.com/docs/analysis-types/multiphase-fluid-flow-analysis/) analysis, which is inherently a transient analysis type. With the *Local time stepping* option enabled, it’s possible to accelerate the simulation towards a steady-state. As a result, faster computing times and smaller result data size.

This option is commonly used in ship hull resistance analysis, to accelerate the simulation towards a steady-state showing wave patterns.

In SimScale, cavitation can be modeled in [multi-purpose simulations](https://www.simscale.com/docs/analysis-types/subsonic-cartesian/) using the **constant gas mass fraction** model.

> [Cavitation Model](https://www.simscale.com/docs/simulation-setup/global-settings/cavitation/)

<iframe title="“Cavitation Model” — SimScale" src="https://www.simscale.com/docs/simulation-setup/global-settings/cavitation/embed/#?secret=ijGVYvHA1G#?secret=qspcwsWHRd" width="500" height="282" frameborder="0"></iframe>

While working with the [multi-purpose solver](https://www.simscale.com/docs/analysis-types/subsonic-cartesian/), it is possible to toggle on **multiphase** in the global settings. The multi-purpose multiphase solution is a based on the Volume Of Fluid (VOF) method, allowing you to simulate time-dependent studies with two phases.

> [Multi-purpose Multiphase](https://www.simscale.com/docs/analysis-types/multi-purpose-analysis/multiphase/)

<iframe title="“Multi-purpose Multiphase” — SimScale" src="https://www.simscale.com/docs/analysis-types/multi-purpose-analysis/multiphase/embed/#?secret=3iEBCSbJd0#?secret=krVN37sX0s" width="500" height="282" frameborder="0"></iframe>

Another option available for the [multi-purpose solver](https://www.simscale.com/docs/analysis-types/subsonic-cartesian/) is the **multicomponent** module. This module is useful when simulating multiple gases in the same flow region, with the objective of analyzing how they mix. The multicomponent module allows you to use different material properties for each of the gases, which is an advantage over the passive species workflow.

> [Multi-purpose Multicomponent](https://www.simscale.com/docs/analysis-types/multi-purpose-analysis/multicomponent/)

<iframe title="“Multi-purpose Multicomponent” — SimScale" src="https://www.simscale.com/docs/analysis-types/multi-purpose-analysis/multicomponent/embed/#?secret=EGbnCAuRxt#?secret=kSNHGzXiPU" width="500" height="282" frameborder="0"></iframe>

The electromagnetic radiation emitted by the sun is also referred to as solar radiation. In CFD, solar radiation acts as an additional heat source. For some applications, such as thermal comfort studies, ignoring solar radiation may impact the accuracy of the results.

SimScale has a solar radiation module in the Conjugate Heat Transfer (CHT) [analysis type](https://www.simscale.com/docs/analysis-types/#fluid-dynamics-openfoam).

> [Solar Load](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/solar-load/)

<iframe title="“Solar Load” — SimScale" src="https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/solar-load/embed/#?secret=gXBlWuBUAi#?secret=EsX1M1IeCA" width="500" height="282" frameborder="0"></iframe>

Exclusive for the [Conjugate Heat Transfer](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/) simulation, when enabled, it includes the humidity effects and related computations as part of the simulation. In order to use it, it requires the *Compressible* toggle to be active beforehand.

When enabled, the model will take into account the transport of the humidity in the domain, as well as its influence on the mixed fluid density. Also, the result fields will include the *Percentage of Relative Humidity*, Absolute Humidity, and *Specific Humidity*.

> [Relative Humidity](https://www.simscale.com/docs/simulation-setup/global-settings/humidity-modeling/)

<iframe title="“Relative Humidity” — SimScale" src="https://www.simscale.com/docs/simulation-setup/global-settings/humidity-modeling/embed/#?secret=4QvRuuQuER#?secret=LZKDUo10QX" width="500" height="282" frameborder="0"></iframe>

Exclusive for the [Conjugate Heat Transfer](https://www.simscale.com/docs/analysis-types/conjugate-heat-transfer-analysis/) and [Conjugate Heat Transfer (IBM)](https://www.simscale.com/docs/analysis-types/immersed-boundary-analysis/) simulations, when enabled, it solves the electric fields and takes the resulting thermal losses into account when solving the overall thermal and flow fields. Electric Potential, Current Density, and *Joule Heat Generation* will be included as additional result fields.

> [Joule Heating](https://www.simscale.com/docs/simulation-setup/global-settings/joule-heating/)

<iframe title="“Joule Heating” — SimScale" src="https://www.simscale.com/docs/simulation-setup/global-settings/joule-heating/embed/#?secret=auL9AdAdOR#?secret=NMVvy2wQnn" width="500" height="282" frameborder="0"></iframe>

## Finite Element Analysis

In case the model’s displacement response to a given load can be assumed to be linear (usually the case for small loads or displacements), keep this setting disabled. Otherwise, when the relationship between applied forces and the displacement response can’t be assumed to be linear, enable the nonlinear analysis setting.

The *Nonlinear analysis* toggle is available for [static](https://www.simscale.com/docs/analysis-types/static/), [heat transfer](https://www.simscale.com/docs/analysis-types/heat-transfer/), and [thermomechanical](https://www.simscale.com/docs/analysis-types/thermomechanical/) analysis types.

> [When Do I Need a Nonlinear Static Analysis?](https://www.simscale.com/knowledge-base/when-do-i-need-a-nonlinear-static-analysis/)

<iframe title="“When Do I Need a Nonlinear Static Analysis?” — SimScale" src="https://www.simscale.com/knowledge-base/when-do-i-need-a-nonlinear-static-analysis/embed/#?secret=wugUjcY1fn#?secret=OUQaKBsLz8" width="500" height="282" frameborder="0"></iframe>

[Heat transfer](https://www.simscale.com/docs/analysis-types/heat-transfer/) and [thermomechanical](https://www.simscale.com/docs/analysis-types/thermomechanical/) analysis can be performed as *Steady-state* and *Transient* simulations. Transient analysis accounts for time-dependent effects, whereas steady-state analysis returns only the converged steady-state solution.

*Inertia effects* refer to the mass times acceleration forces that are developed during movement with varying speeds. It is equivalent to performing a [*Dynamic*](https://www.simscale.com/docs/analysis-types/dynamic/) simulation in the mechanical part of the solution. Set this if there are considerable accelerations in the model.

This setting is available in transient [thermomechanical](https://www.simscale.com/docs/analysis-types/thermomechanical/) analysis settings, where the inertia effects are only considered when the simulation type is set to *Dynamic*. Otherwise, if set to *Static*, inertia effects won’t be taken into account.

Last updated: May 21st, 2025

What's Next

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries