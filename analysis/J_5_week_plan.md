# J 5 Week Plan

## Goal

Design a VAWT, model it in 3D with Zoo Keeper or another agentic modeling tool, test it through simulation, and write a report on the final design.

## Starting Point

- Current progress: the wiki has been set up and now acts as the research base for the design project.
- Working assumption: the project should follow a site-first, concept-second, geometry-third, validation-fourth, optimization-last workflow. (source: sources/HRI2526.md, sources/vj21.md, sources/vj6.md)

## Week 1: Define Scope And Choose A Direction

### Main goal

Turn the wiki and wind data into a design brief and choose one VAWT concept to pursue.

### Tasks

- Summarize the site and wind regime in one page.
- Decide which turbine family to pursue: Savonius, Darrieus/H-rotor, helical, or hybrid.
- Define project success criteria.
- Choose one baseline concept and one backup concept.

### How to accomplish it

- Use the wind data and the wiki pages on [[Urban Wind Conditions]], [[Annual Energy Output]], [[Wind Turbine Parameters]], and [[Rules of Thumb]] to define the operating environment and what matters most.
- Use [[Design Checklist]] and [[VAWT Design Overview]] to make sure the concept choice is tied to the site, not just to preference.
- Keep the concept comparison simple: startup behavior, expected energy production, manufacturability, modeling difficulty, and testability.

### Deliverables

- One-page design brief
- Concept comparison table
- Final selected concept and one backup

### What I can help with

- Turn the wind data into a short design brief
- Compare concepts using the wiki
- Build a concept comparison table
- Help decide which concept to carry forward

## Week 2: Set Geometry And Build The First 3D Models

### Main goal

Define the first-pass geometry and create the baseline 3D model plus one alternate variant.

### Tasks

- Pick the main geometry parameters for the chosen concept.
- Make a baseline 3D model.
- Make one alternate version with a limited set of changes.
- Record all dimensions in a parameter table.

### How to accomplish it

- Use [[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]], [[Wind Turbine Parameters]], [[Design Checklist]], and relevant source-specific pages for the chosen concept.
- If the concept is a small fixed-pitch straight-bladed VAWT, explicitly review airfoil, blade count, strut shape, solidity, aspect ratio, chord-radius ratio, loads, material, noise, and aesthetics before freezing geometry. (source: sources/vj21.md)
- Keep the alternate design close to the baseline so the comparison is clean.
- Build only what is necessary to compare two meaningful versions rather than creating many rough variants.

### Deliverables

- Baseline 3D model
- One alternate 3D model
- Geometry / parameter table

### What I can help with

- Translate wiki findings into a design parameter sheet
- Suggest which parameters should change first
- Help structure prompts or specs for Zoo Keeper / agentic modeling
- Review the geometry for obvious design problems

### Note

> Unverified: the repo does not contain a source-backed workflow for Zoo Keeper specifically, so the modeling-tool details here are planning guidance rather than source-grounded method.

## Week 3: Analyze The Designs And Select A Final Candidate

### Main goal

Run first-pass analysis and choose the one design that deserves physical testing.

### Tasks

- Run CFD or another modeling pass on the baseline and alternate design.
- Compare results across the expected operating band.
- Evaluate startup behavior, relative performance, manufacturability, and structural plausibility.
- Select one final candidate for prototyping.

### How to accomplish it

- Use [[CFD]] and [[CFD and Validation]] as the method guide.
- Focus on the wind-speed range your site actually sees instead of optimizing for a rare best-case condition. (source: sources/va1.md, sources/vj13.md, sources/HRI2526.md)
- Compare designs with a short matrix rather than many separate notes.
- Record assumptions clearly, especially if the modeling is simplified or only partially validated.

### Deliverables

- Analysis comparison table
- Final candidate selection
- Short risk / uncertainty list

### What I can help with

- Review CFD assumptions and outputs
- Build a results comparison matrix
- Help interpret analysis against the site wind regime
- Help write the final-selection rationale

## Week 4: Expand Simulation Testing And Refine The Design

### Main goal

Use simulation-only testing to stress the chosen design, compare operating conditions, and refine the final geometry.

### Tasks

- Build a simulation test matrix before running the final round of cases.
- Run the chosen design across the most important wind-speed range and operating conditions.
- Check startup-related behavior, relative performance trends, and any obvious instability or sensitivity.
- Document failure modes, weak operating regions, and unexpected behavior.

### How to accomplish it

- Use [[CFD]], [[CFD and Validation]], and [[Wind Tunnel Testing]] as method references for what performance quantities and validation logic matter, even though the project itself will stay fully digital.
- Decide in advance what simulation cases matter most: wind-speed steps, TSR range, startup-oriented conditions, and any geometry variants still under consideration.
- At minimum, extract the quantities you need for comparison such as startup tendency, `Cp`, torque, rotational-speed trend, and any strong unsteady behavior.
- Use this week to reduce uncertainty in the final design rather than to explore many new concepts.

### Deliverables

- Simulation test matrix
- Results table for the final design across key cases
- Basic plots such as wind speed versus startup tendency / `Cp` / rpm / torque if available
- Short summary of what worked, what failed, and what changed in the design

### What I can help with

- Write the simulation test matrix
- Organize result tables
- Make plots from simulation outputs
- Draft methods and results text while you run cases

## Week 5: Freeze The Design And Write The Report

### Main goal

Finalize the design and produce a clear report explaining what you designed, why, how you modeled it, how you tested it, and what you learned.

### Tasks

- Freeze the final geometry and design justification.
- Re-check the design against the checklist and rules of thumb.
- Write the report.
- Summarize limitations and next steps honestly.

### How to accomplish it

- Revisit [[Design Checklist]], [[Rules of Thumb]], [[Annual Energy Output]], [[CFD]], and [[Wind Tunnel Testing]].
- Structure the report in this order:
  - problem and site context
  - concept selection
  - design choices
  - modeling method
  - simulation testing method
  - results
  - final design
  - limitations
  - next steps
- Start writing before the week begins if possible, so Week 5 is mostly refinement rather than writing from scratch.

### Deliverables

- Final report draft
- Final figures and tables
- Final design summary

### What I can help with

- Outline the report
- Draft sections from your notes and results
- Edit for structure and clarity
- Turn raw results into tables, figures, and captions

## Best Practical Sequence

1. Choose one concept by the end of Week 1.
2. Limit Week 2 to one baseline and one alternate design.
3. Use Week 3 to decide on one final candidate, not to keep expanding options.
4. Treat Week 4 as minimum viable testing, not perfect testing.
5. Start report writing in Week 3 so Week 5 is focused on revision and completion.

## What I Can Help With Across The Whole Project

- Turn the wiki into a focused design brief
- Compare VAWT concepts and choose a direction
- Build parameter tables and decision matrices
- Review geometry choices against the sources
- Help structure prompts/specs for your modeling workflow
- Review CFD and simulation test plans
- Analyze wind data and connect it to design decisions
- Draft and edit the final report

## Uncertain

- The repo supports the design workflow, testing logic, and validation sequence, but it does not contain a source-backed workflow for Zoo Keeper specifically.
- The plan now assumes a fully digital workflow with no physical prototype stage.
- The exact depth of modeling and simulation testing you can reach in five weeks depends on what tools, compute access, and solver workflow you actually have.
