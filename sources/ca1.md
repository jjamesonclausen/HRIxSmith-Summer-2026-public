---
title: "SimScale Platform Introduction"
source: "https://www.simscale.com/docs/platform/"
author:
published: 2018-10-30
created: 2026-07-15
description: "Navigate through the user-friendly SimScale platform & dashboard, learn how to find other helpful pages like our blog, case studies, & more."
tags:
  - "clippings"
---
Documentation

## Platform Introduction

Welcome! This page introduces the basics of how the SimScale Workbench functions and how to navigate through the platform interface. We at SimScale aim to become *the hub* for all things simulation.

## Overview

The following pages might be of interest to you:

- [**SimScale Blog**](https://www.simscale.com/blog/): In the SimScale blog we write about the latest trends in the simulation industry, showcase simulation use cases, introduce new features, and much more…
- [**Webinars & Workshops**](https://www.simscale.com/webinars-workshops/): In case you want to attend one of our live webinars or workshops, find all past and upcoming events here.
- [**Case Studies**](https://www.simscale.com/customers/): Many customers worldwide use SimScale as their main simulation tool. Find out more about how they use SimScale to streamline their design process.

Here we’ll focus on explaining the basics about the **SimScale Community** and **Workbench**. The SimScale Community entails all components in which our large base of users can interact with each other, share their simulation projects and ask questions as well as discuss the future development of the platform and the simulation industry as a whole. It’s split into the following components:

- [**SimScale Community Forum**](https://www.simscale.com/forum/): In case you find yourself stuck or need answers to a simulation-related question, there’s a good chance that you’ll find the answer in the SimScale Forum.
- [**Public Projects Library**](https://www.simscale.com/projects/): We at SimScale believe that simulation should be accessible to everybody. In order to achieve that goal, SimScale offers a free unlimited Community Plan to every new user. Any simulation project that is created as part of the community plan will be publicly available and may be listed in the [Public Projects Library](https://www.simscale.com/projects/). You can copy any of the thousands of public simulation projects and use them as templates for your own simulation application. In order to simulate privately and for access to more advanced features, check our [Plans & Pricing](https://www.simscale.com/product/pricing/) page or [contact support](https://www.simscale.com/contact-us/).
- **Dashboard**: The dashboard is your private hub containing all your simulation projects as well as projects that have been shared with you. From here you are able to open your projects in the SimScale Workbench as well as create a new project from scratch. More about the Dashboard below.
- **Workbench**: The SimScale simulation platform (or *“Workbench”*) is the heart of SimScale. Here is where the magic happens. We’ll explain the basics of the Workbench below.

This is just a short overview of SimScale. Let’s dive into the details of how to use the dashboard and the workbench.

## Dashboard

![simscale dashboard with organization ](https://frontend-assets.simscale.com/media/2024/01/new-dashboard-2-1024x447.png)

Figure 1: The SimScale Dashboard. Find here an overview of your account as well as all your simulation projects.

The **Dashboard** is your personal landing page when you log into your SimScale account. It contains the spaces, folders, projects, your account details and activity. Her you can organize your content allowing you to quickly and easily find the correct project while ensuring that only the correct people can access it. This is also the place where a new project can be created.

<iframe title="“Dashboard” — SimScale" src="https://www.simscale.com/docs/platform/dashboard-folders-and-spaces/embed/#?secret=OLjbHv7onr#?secret=PvvuqG1v2e" width="500" height="498" frameborder="0"></iframe>

Once the project is created, you’ll automatically be redirected to the SimScale simulation platform i.e. the Workbench.

## Workbench

The SimScale Workbench is a single interface that supports a variety of different [analysis types](https://www.simscale.com/docs/analysis-types/). A central concept of the Workbench is the organization of simulation setup parameters as per analysis type. This helps keep the simulation tree or the setup short and compact, by only exposing use-case-compatible settings of the solver in the interface.

Besides basic CAD manipulation features, it contains the simulation and mesh setup as well as the online post-processor.

![SimScale workbench/platform with static analysis](https://frontend-assets.simscale.com/media/2021/01/workbench-layout-1024x469.jpg)

Figure 2: The SimScale Workbench. Here you can prepare your CAD models for simulation, specify simulation setups, and visualize (post-process) your simulation results.

Here is a short description of the main interface components of the Workbench. The nomenclature introduced here will be used throughout the documentation.

1. **Navigation Tree**: The simulation tree occupies the whole left-side panel of the workbench and contains a list of all geometries (CAD models) and meshes that were imported into the project at the top (**“Geometry Tree”**) as well as a list of all simulations below (**“Simulation Tree”**). One project can contain multiple geometries and simulations. Each simulation is represented in the form of a tree. The tree, depending on the [analysis type](https://www.simscale.com/docs/analysis-types/) chosen, will expose all settings that are required to start the simulation. It’s advised to complete the simulation set up along the tree from top to bottom.
2. **Settings Panel**: The settings panel is where you can actually change the setup of your simulations. Click on a node in the tree to open the respective settings panel. Use the checkmark button at the top of the panel to save any changes and close the panel (or simply hit *Enter*). Click the close button to simply close and discard any changes made (or hit *Esc*). Note that your changes will automatically be saved if you navigate to another settings panel via the simulation tree.
3. **Scene Tree**: The scene tree represents the model as displayed in the viewer (see below). It lists the geometry or mesh that is currently in context, including all solid bodies, sheet bodies, and faces. It’s also possible to create sets ([topological entity sets](https://www.simscale.com/docs/topological-entity-sets/)) of entities in the scene tree, for more convenient selection later on. Besides the original geometry and the entity sets, the scene tree also lists geometry primitives created from within the Workbench. These [geometry primitives](https://www.simscale.com/docs/simulation-setup/model/geometry-primitives/) are usually used to define areas for mesh refinement or applying *[advanced concepts](https://www.simscale.com/docs/simulation-setup/advanced-concepts/)*.
4. **Viewer Toolbar**: The viewer toolbar (from left to right) contains the main controls for interacting with the viewer. Besides the *view mode* and *render mode* controls, the viewer toolbar’s primary controls include the selection mode picker. Here you can choose whether to select whole bodies (volumes), faces, edges, or nodes, which is often required to properly define your simulation setup. The viewer toolbar also contains the toggle for *box selection* as well as the *mesh clip* feature.
5. **Chat Box**: The chatbox is extremely helpful if you are stuck with your project or simply need to connect and discuss with the SimScale support team. You can choose to [share your project](https://www.simscale.com/docs/platform/collaboration/#share-project-with-support) with the support team as well.
6. **Orientation Cube**: The cube on the bottom right shows the orientation of the geometry with respect to the x-, y-, z-coordinate system. Interact with your geometry either using the buttons around the cube or simply using the mouse.
7. **Viewer**: The viewer is the core of the interface. It contains the entire scene of the simulation, including the original geometry (or mesh) as well as any additional geometry primitives. Use the viewer to inspect your setup and to make selections and assignments.
8. **Job Status Panel**: Here you can find the current status of your meshing and simulation jobs. Any computation-intensive operation that you start in the Workbench will not be computed using your local hardware, but will be run on a cloud computing instance. The job status panel reports on the current status of all job operations as well as their current run time and core hour consumption.

One of the main benefits of a web-based simulation platform is the possibility it provides for collaboration with fellow users. Find out more about [SimScale’s collaboration features](https://www.simscale.com/docs/platform/collaboration/).

Here are a few helpful tips that will make it easier to get familiar with the SimScale Workbench:

- Use the ‘ **+** ‘ icons in the simulation tree to upload a new geometry, create a new simulation or to create additional attributes (like boundary conditions) in your simulation setup.
- Always try to work through the simulation tree **from top to bottom**. Any tree node with a red circle icon requires additional to be specified, while a red crossed icon indicates an error in the setup. A blue circle indicates an optional setting. Only if all tree nodes show a green checkmark, your simulation setup is complete and a simulation run can be started.
- If necessary, go ahead and change the setup with your simulation parameters and assignments while the mesh is computing. **Don’t wait for your meshing job to be completed.** You can even start multiple meshes at the same time and later choose the one that best fits your use case.
- For more tips and tricks visit our [knowledge base article](https://www.simscale.com/knowledge-base/selection-via-the-viewer-tips-tricks/).

Now you should be all set to start your first simulation. Go ahead and choose one of our [guided simulation tutorials](https://www.simscale.com/tutorials/).

## API and SDK

All the links to the SimScale associated API and SDK can be found below:

<iframe title="“API and SDK Documentation in SimScale” — SimScale" src="https://www.simscale.com/docs/platform/api-and-sdk-documentation/embed/#?secret=QdJlJ5byde#?secret=XRubcdpAb7" width="500" height="214" frameborder="0"></iframe>

Last updated: July 22nd, 2025

Product

What is SimScale?

Technology

Solutions

Use cases

Applications

Industries