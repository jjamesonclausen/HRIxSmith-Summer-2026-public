---
Created: 2026-07-08
Updated: 2026-07-08
Sources: [[HRI2526]], [[va10]], [[vj11]], [[vj18]], [[vj21]]
Source_count: 5
Tags:
---
## Work Plan A1

This page turns the current BOS design direction into three scoped work plans: `1` week, `4` weeks, and `5.5` weeks.

## Grounded Constraints

- The current BOS target is Boston Logan International Airport, using wind data collected at `9 m` above ground; the design brief notes an average wind speed of `4.8 m/s`, average gusts of `6.3 m/s`, and a likely need to use a `5`-year span for annual-energy calculations because the sample year has gaps. (source: active/analysis/Design goal.pdf)
- The BOS brief also says siting remains unresolved because runway-area restrictions, rooftop placement limits, and allowable turbine count still need to be checked. (source: active/analysis/Design goal.pdf)
- The BOS brief notes that many Darrieus turbines have rated speeds around `10-15 m/s`, while the `va9 EN0005` concept appears to have a much lower cut-in speed, below `2 m/s`, which matters for a lower-wind site. (source: active/analysis/Design goal.pdf)
- The same brief says the turbine should ideally be designed near the wind-measurement height because wind speed can vary strongly within the near-ground boundary layer. (source: active/analysis/Design goal.pdf)
- The prior HRI/Smith phase found that concept narrowing, CFD setup, troubleshooting, and validation consumed substantial time even before a design was ready for high-confidence conclusions. (source: sources/HRI2526.md)
- That phase also recommended improving the testing workflow, exploring higher-wind environments, and advancing CFD fidelity before putting too much confidence in detailed performance claims. (source: sources/HRI2526.md)
- The CFD review material says grid independence, domain-size sensitivity, and validation against reference data should be done before trusting performance outputs. (source: sources/va10.md)
- The VAWT CFD review says `2D` URANS can overpredict `Cp` by about `15-30%` relative to validated `3D` simulations, so simulation speed and simulation trust are in tension. (source: sources/vj11.md)
- The variable-design review says many promising VAWT results remain simulation-heavy and need stronger validation before commercialization-style confidence is justified. (source: sources/vj18.md)
- The fixed-pitch straight-bladed design guide says a serious pre-freeze review should explicitly cover airfoil, blade count, strut shape, solidity, aspect ratio, materials, loads, noise, and aesthetics. (source: sources/vj21.md)

> Unverified: The current project brief in chat says the team is `2` undergraduate students, working `40` hours each per week until `2026-08-14`, using Zoo Design Studio plus Zookeeper for CAD, SimScale for CFD, with access to help from Honda Research Institute and oversight from a Smith College professor. The plans below assume that brief is accurate, but that information is not yet captured in a repo source file.

> Inference: Because BOS is a moderate-wind site, your team is new to CAD and CFD, and prior HRI work shows validation can eat large amounts of schedule, the safest planning strategy is to lock one realistic design path early, validate the simulation workflow early, and treat optimization as secondary until the baseline is trusted.

## Plan A: One Week

Goal: leave the week with one defended design direction, one baseline CAD model, one validated CFD workflow plan, and one clear report outline.

Recommended when:
- you need a fast decision sprint
- you want to avoid spending the week on premature geometry optimization
- you need a strong check-in package for Honda and your professor

Scope:
- Hours assumed: about `80` team-hours total. (> Unverified: based on the current chat brief)
- Main output: a downselected baseline concept plus a credible simulation plan, not a polished final-performance claim. (> Inference)

Day-by-day structure:

1. Day 1: Lock requirements and decision criteria.
- Define the site case, target installation height, target wind-speed range, and success metrics for `Cp`, cut-in behavior, AEO method, manufacturability, and siting realism. (source: active/analysis/Design goal.pdf, sources/HRI2526.md)
- Translate those into a short scoring matrix for `3-4` candidate turbine families or candidate designs already in the wiki. (source: sources/HRI2526.md, sources/vj21.md)

2. Day 2: Downselect the concept.
- Compare at least one low-risk self-starting path, one higher-efficiency Darrieus path, and one hybrid path. (source: active/analysis/Design goal.pdf, sources/HRI2526.md)
- Make a formal decision by end of day, with one backup concept kept only as a contingency. (> Inference)

3. Day 3: Build baseline CAD.
- Create the first full rotor CAD for the chosen concept at the intended analysis scale.
- Freeze only the geometry needed for CFD setup: rotor diameter, height, blade count, blade profile family, and major support geometry. (source: sources/vj21.md)

4. Day 4: Build a minimal CFD baseline.
- Set up one baseline SimScale case aimed at workflow validation rather than optimization.
- Do not run a large sweep yet; first confirm rotating-domain setup, boundary conditions, mesh behavior, and output extraction. (source: sources/HRI2526.md, sources/va10.md, sources/vj11.md)

5. Day 5: Review and plan next steps.
- Meet with Honda or your professor using a short package: chosen concept, why it fits BOS, current CAD screenshots, CFD setup screenshots, known risks, and the next parameter study. (> Unverified: assumes advisor availability from the project brief)
- End the week with a written `go / revise / pivot` decision. (> Inference)

Deliverables by end of week:
- one concept-selection memo
- one baseline CAD model
- one CFD setup and validation checklist
- one parameter-study shortlist
- one report skeleton with section owners

Main risk:
- Losing the week to CFD troubleshooting before the concept is actually locked. (source: sources/HRI2526.md)

## Plan B: Four Weeks

Goal: finish one defendable turbine design with a baseline CAD model, a validated CFD workflow, a focused parameter sweep, and a first-pass BOS performance estimate.

Recommended when:
- you can spend `4` full weeks before switching heavily into report writing
- you want one credible design study rather than multiple shallow concepts

Scope:
- Hours assumed: about `320` team-hours total. (> Unverified: based on the current chat brief)
- Main output: one selected turbine concept with simulation-backed comparative results and a first-pass annual-energy estimate. (> Inference)

Week-by-week structure:

1. Week 1: Requirements, siting frame, and concept lock.
- Finalize BOS assumptions, including measurement height, wind dataset choice, and what siting questions remain unresolved. (source: active/analysis/Design goal.pdf)
- Downselect to one primary concept and one backup concept. (source: sources/HRI2526.md)
- Build the baseline CAD and define the exact parameter list you may vary later. (source: sources/vj21.md)

2. Week 2: CFD workflow validation.
- Validate the modeling approach before optimization: mesh sensitivity, domain sanity, solver stability, and at least one comparison against literature behavior or a simpler validation case. (source: sources/va10.md, sources/vj11.md, sources/HRI2526.md)
- If the workflow is not credible by the end of Week 2, reduce ambition and switch to a smaller, cleaner comparative study rather than a broad optimization. (> Inference)

3. Week 3: Focused parameter study.
- Run a small sweep over only the parameters most likely to matter for the selected concept, such as blade profile, pitch, blade count, solidity, or aspect ratio depending on concept family. (source: sources/vj21.md)
- Keep the sweep narrow enough that every case can be checked for mesh/solver sanity. (source: sources/va10.md)

4. Week 4: Downselect final design and estimate performance.
- Pick the best-performing configuration from the validated sweep.
- Estimate BOS-relevant performance using the site wind regime and state uncertainty clearly, especially if the result is still based mainly on CFD. (source: active/analysis/Design goal.pdf, sources/vj18.md, sources/vj11.md)
- Draft the core technical figures and tables for the report.

Suggested division of labor:
- Student A: CAD owner, geometry tracking, figure generation, report integration.
- Student B: CFD owner, case management, post-processing, result tables.
- Shared: concept selection, wind-data interpretation, advisor meetings, and final claims review. (> Inference)

Deliverables by end of four weeks:
- one selected design with version history
- one validated baseline CFD workflow
- one limited parameter sweep with conclusions
- one BOS performance estimate with uncertainty notes
- a half-complete report draft

Main risk:
- Running too many CFD cases before the baseline is validated, which creates a lot of output but little trust. (source: sources/va10.md, sources/vj18.md)

## Plan C: Full Five-and-a-Half Weeks

Goal: finish a report-ready turbine design study with stronger traceability, clearer uncertainty bounds, and a serious reflection on how the AI tools helped or hurt the process.

Recommended when:
- you want the strongest final report, not just the fastest technical result
- you want time for one iteration after advisor feedback
- you want to explicitly document your use of the wiki, CAD AI tools, and SimScale AI features

Scope:
- Hours assumed: about `440` team-hours total. (> Unverified: based on the current chat brief)
- Main output: one report-ready design package with a validated modeling story, BOS framing, design rationale, and an AI-tool retrospective. (> Inference)

Week-by-week structure:

1. Week 1: Frame the project and lock the concept.
- Turn the BOS brief into explicit engineering requirements and decision criteria. (source: active/analysis/Design goal.pdf)
- Downselect to one primary concept and one fallback concept. (source: sources/HRI2526.md)
- Freeze the initial CAD baseline.

2. Week 2: Validate the simulation workflow.
- Build the minimum trustworthy CFD process first: boundary conditions, rotating region, mesh strategy, convergence checks, and one validation comparison. (source: sources/va10.md, sources/vj11.md, sources/HRI2526.md)
- Hold a technical review with Honda support focused only on CFD credibility, not final performance claims. (> Unverified: assumes support availability from the current chat brief)

3. Week 3: Run the main parameter study.
- Sweep only the highest-value parameters for the chosen rotor family.
- Keep a written case log so you can defend why each geometry change was tested and why others were deferred. (> Inference)

4. Week 4: Refine and downselect.
- Pick the best configuration.
- If time permits, run one confirmation pass at higher fidelity or tighter mesh on the best case rather than adding many new cases. (source: sources/va10.md, sources/vj11.md)
- Start building final report figures as you go.

5. Week 5: BOS performance story and report drafting.
- Combine the selected design with the BOS wind framing and annual-energy method.
- Write the technical report sections on site, concept selection, CAD workflow, CFD workflow, results, and uncertainty. (source: active/analysis/Design goal.pdf, sources/vj18.md)
- Add an explicit section on what the AI tools accelerated, where they created overhead, and where human review was still essential. (> Inference)

6. Final half week: Review, tighten, and package.
- Do a full claim audit so the report separates source-backed findings from inference.
- Ask Honda and your professor for one last review pass on the main conclusions. (> Unverified: assumes review availability from the current chat brief)
- Finalize slides, figures, appendix material, and the AI-process reflection.

Deliverables by end of `5.5` weeks:
- final chosen turbine design
- validated simulation workflow narrative
- focused comparative performance study
- BOS-specific annual-energy framing
- final report draft and presentation material
- explicit AI-tool reflection with lessons learned

Main risk:
- Letting the longer schedule justify too much exploration, which can delay the validated final story instead of improving it. (> Inference)

## Recommendation

> Inference: The strongest path is the `5.5`-week plan, but it should be run with the discipline of the `4`-week plan. In practice that means using Week `1` to lock the concept, Week `2` to validate CFD, Weeks `3-4` to do only the highest-value parameter study, and reserving the last `1.5` weeks for downselection, uncertainty, and writing. If validation is still shaky by the end of Week `2`, fall back to the `4`-week plan logic and reduce the sweep.

Related:
- [[Design Checklist]]
- [[Turbine Concept Selection]]
- [[CFD and Validation]]
- [[Annual Energy Output]]

#concepts
