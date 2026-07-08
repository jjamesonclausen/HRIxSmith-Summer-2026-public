# J Two Week Plan

## Goal

Design a VAWT, model it in 3D with Zoo Keeper or another agentic modeling tool, test it through simulation only, and write a short final report on the chosen design.

## Starting Point

- Current progress: the wiki is set up and can now be used as the design knowledge base.
- Constraint: only two weeks are available, so the project needs one concept, one main design loop, one refinement pass, and one final report.
- Working assumption: the project should still follow a site-first, concept-second, geometry-third, validation-fourth workflow, but in compressed form. (source: sources/HRI2526.md, sources/vj21.md, sources/vj6.md)

## Strategy

Because the timeline is short, the project should avoid broad exploration.

Do this:
- pick one concept quickly
- build one baseline model
- make one alternate variant only
- compare them with simulation
- pick one final design
- write the report immediately after the comparison

Do not do this:
- do not explore many turbine families
- do not build several weak variants
- do not wait until the end to start writing

## Week 1: Choose, Define, And Build

### Main goal

Choose one VAWT direction, define the first-pass geometry, and create the baseline and alternate 3D models.

### Tasks

- Summarize the site and wind regime in a short design brief.
- Choose the turbine family and freeze the decision.
- Define the first-pass geometry and performance goals.
- Build one baseline 3D model.
- Build one alternate version with only a few key changes.

### How to accomplish it

- Use [[Urban Wind Conditions]], [[Wind Turbine Parameters]], [[Annual Energy Output]], [[Rules of Thumb]], [[VAWT Design Overview]], and [[Design Checklist]] as the main decision pages.
- Make the concept decision early. If self-starting and low-speed behavior matter more than top efficiency, the wiki says Savonius or hybrid concepts deserve serious attention. (source: sources/vj2.md, sources/n2.md)
- If you choose a small fixed-pitch straight-bladed VAWT, explicitly review airfoil, blade count, strut shape, solidity, aspect ratio, chord-radius ratio, loads, material, noise, and aesthetics before freezing geometry. (source: sources/vj21.md)
- Keep the alternate version simple. Change only the highest-value parameters rather than redesigning the whole turbine.
- Start a report outline at the end of the week so the project does not stall in Week 2.

### Deliverables

- One-page design brief
- Concept choice with short justification
- Baseline 3D model
- One alternate 3D model
- Geometry / parameter table
- Report outline

### What I can help with

- Turn your wind data into a short design brief
- Compare concepts and help choose one
- Build a concept comparison table
- Suggest which geometry parameters to define first
- Help structure prompts/specs for Zoo Keeper or another modeling tool
- Review the baseline and alternate design logic

## Week 2: Simulate, Select, And Write

### Main goal

Run simulation-based comparison, choose the final design, and write the report.

### Tasks

- Run the baseline and alternate design through your simulation workflow.
- Compare them across the most important operating conditions.
- Select one final candidate.
- Run one final refinement or confirmation pass on the chosen design if time allows.
- Write the report around the final design and results.

### How to accomplish it

- Use [[CFD]] and [[CFD and Validation]] to guide what assumptions and outputs matter.
- Focus on the wind-speed range your site actually sees instead of chasing a best-case condition that rarely occurs. (source: sources/va1.md, sources/vj13.md, sources/HRI2526.md)
- Compare designs with a short matrix using a few core metrics only, such as startup tendency, relative performance, stability, and design practicality.
- Use Week 2 writing as you go:
  - first write methods while simulations are running
  - then fill in results and discussion as outputs come in
  - end with limitations and next steps
- If there is time for only one more pass after the comparison, refine the selected design rather than continuing to compare more concepts.

### Deliverables

- Simulation comparison table
- Final selected design
- Short final refinement if completed
- Final report draft
- Final figures and result summaries

### What I can help with

- Review CFD/simulation assumptions
- Build a comparison matrix for simulation outputs
- Help interpret results against your wind regime
- Draft the methods, results, and discussion sections
- Edit the report for clarity and structure

## Minimum Viable Report Structure

Use this order:

1. problem and site context
2. concept selection
3. design choices
4. modeling method
5. simulation testing method
6. results
7. final design
8. limitations
9. next steps

## Priority Order

If time gets tight, keep this order:

1. choose one concept
2. build one baseline model
3. build one alternate model
4. simulate both
5. select one final design
6. write the report

If something must be cut, cut extra variants and extra refinement, not the comparison step or the report.

## What I Can Help With Across Both Weeks

- turn the wiki into a design brief
- help choose the turbine concept
- create parameter tables and decision matrices
- review geometry choices against the sources
- help structure prompts/specs for your modeling workflow
- review CFD and simulation assumptions
- analyze results and compare variants
- draft and edit the final report

## Uncertain

- The repo supports the design workflow, validation logic, and reporting structure, but it does not contain a source-backed workflow for Zoo Keeper specifically.
- The exact depth of the simulation work depends on what modeling and compute resources are available in the two-week window.
- With only two weeks, this plan is optimized for a credible final concept and report, not for exhaustive optimization.
