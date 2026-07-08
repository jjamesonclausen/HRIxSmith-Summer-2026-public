---
Created: 2026-07-08
Updated: 2026-07-08
Tags: #planning
---
## Work Plan A2

This note turns the `5.5`-week path from [[Work Plan A1|Work Plan A1]] into a dated working calendar.

Technical sequencing is based on [[CFD and Validation]], [[Design Checklist]], and the BOS framing in `active/analysis/Design goal.pdf`.

> Unverified: The meeting cadence and staffing assumptions below come from the current project brief in chat, not from a repo source file.

## Planning Assumptions

- Project start for this calendar: Wednesday afternoon, `2026-07-08`.
- Five full work weeks begin Monday, `2026-07-13`.
- Final date for this calendar: Friday, `2026-08-14`.
- Daily professor meeting: `9:00 AM` each weekday.
- HRI meeting: Tuesday afternoons.
- HRI is also available through Slack or ad hoc Zoom for troubleshooting when needed.
- Secondary goal: improve your workflow and leave behind reusable project resources, but not at the expense of the main design-and-validation schedule.

## Default Rhythm

- `9:00 AM`: professor standup every weekday.
- Tuesday afternoon: HRI review or technical troubleshooting session.
- End of each day: `20-30` minutes to update the active logs, including the wiki when decisions stabilize, the project log, the CFD case log, and the Zookeeper prompt log.
- If a technical blocker lasts more than about `2` hours, use Slack or a short Zoom check-in instead of losing the full day. (> Inference)

## Kickoff Half Week: 2026-07-08 to 2026-07-10

Weekly goals:
- [ ] Turn the high-level plan into an active working calendar.
- [ ] Set up the minimum project-management and documentation structure.
- [ ] Enter Monday with a clear concept-selection and CFD-validation agenda.

### Wednesday 2026-07-08 Afternoon

- [ ] Review [[Work Plan A1|Work Plan A1]] together and agree that the primary path is concept lock, then CFD validation, then a narrow parameter study.
- [ ] Define the live project folders and logs you will actually maintain: wiki notes, project log, Zookeeper prompt log, CFD case log, and report draft location.
- [ ] Create a short running question list for your professor and HRI.
- [ ] Decide who owns the first pass of CAD organization and who owns the first pass of CFD organization.

### Thursday 2026-07-09

- [ ] Turn the BOS brief into a one-page requirements sheet: site assumptions, target height, target wind range, success metrics, and open siting questions.
- [ ] Make a short candidate list of concepts worth serious consideration next week.
- [ ] Draft the agenda for next Tuesday's HRI meeting so it focuses on decisions you actually need.
- [ ] Set up a lightweight template for the Zookeeper prompt log so useful CAD prompts can be reused later.

### Friday 2026-07-10

- [ ] Finalize the Week 1 decision criteria for concept selection.
- [ ] Prepare the comparison materials you will use on Monday for concept downselection.
- [ ] Clean up the wiki only where it helps next week's decisions; do not spend the day on general wiki maintenance. (> Inference)
- [ ] End the day with a short weekly review: what is ready, what is still ambiguous, and what must be answered next week.

## Week 1: 2026-07-13 to 2026-07-17

Weekly goals:
- [ ] Lock one primary concept and one fallback concept.
- [ ] Freeze the first baseline geometry for CAD and CFD.
- [ ] Enter Week 2 with a credible CFD setup plan, not just a concept idea.

### Monday 2026-07-13

- [ ] Use the morning professor meeting to confirm the Week 1 decision criteria.
- [ ] Compare the short list of concepts against BOS wind conditions, likely siting constraints, manufacturability, and simulation feasibility.
- [ ] Narrow the list to `2-3` serious contenders.
- [ ] Start a decision memo that records why each concept is kept or dropped.

### Tuesday 2026-07-14

- [ ] Use the morning to tighten the comparison and identify the hardest open questions.
- [ ] Meet with HRI in the afternoon and focus on concept risk, manufacturability, and whether your proposed simulation path is realistic for the schedule.
- [ ] Update the decision memo immediately after the HRI meeting while the feedback is still fresh.

### Wednesday 2026-07-15

- [ ] Make the primary concept decision by midday.
- [ ] Keep one fallback concept only if it is genuinely usable, not just emotionally comforting. (> Inference)
- [ ] Define the baseline geometry variables you need to set this week: rotor height, diameter, blade count, airfoil or blade profile family, and major support geometry.
- [ ] Begin the first clean CAD model.

### Thursday 2026-07-16

- [ ] Continue the baseline CAD model.
- [ ] Resolve obvious geometry problems that would complicate meshing or rotating-domain setup later.
- [ ] Capture the key Zookeeper prompts that were actually useful; ignore the rest.
- [ ] Do an afternoon professor check-in on whether the geometry is mature enough to freeze on Friday.

### Friday 2026-07-17

- [ ] Freeze Version `A` of the baseline geometry.
- [ ] Export the files needed for SimScale setup.
- [ ] Write the Week 2 CFD plan: validation case, domain assumptions, mesh plan, outputs to track, and stop/go criteria.
- [ ] End the week with a short review of concept rationale, geometry status, and simulation-readiness risks.

## Week 2: 2026-07-20 to 2026-07-24

Weekly goals:
- [ ] Build a minimum trustworthy CFD workflow.
- [ ] Validate the setup enough to know whether Week 3 should be a real parameter study or a reduced comparative study.
- [ ] Avoid broad optimization until the baseline workflow is behaving sensibly.

### Monday 2026-07-20

- [ ] Build the first full SimScale setup for the baseline design.
- [ ] Confirm the rotating region, boundary conditions, reference velocity choice, and output definitions.
- [ ] Decide what the first validation target will be: a simpler literature-aligned case, a known airfoil case, or a reduced geometry check.

### Tuesday 2026-07-21

- [ ] Run the first baseline case or dry run in the morning.
- [ ] Meet with HRI in the afternoon and focus the conversation on CFD credibility, not final performance claims.
- [ ] Ask directly about any meshing, boundary-layer, or rotating-zone issues that are slowing you down.

### Wednesday 2026-07-22

- [ ] Run mesh and domain sanity checks.
- [ ] Record which settings materially change the result and which do not.
- [ ] Start a clean CFD case log that records setup, reason for each run, and main outputs.

### Thursday 2026-07-23

- [ ] Complete at least one validation comparison.
- [ ] Decide whether the current workflow is trustworthy enough for a parameter sweep.
- [ ] If not, simplify now rather than carrying a weak setup into Week 3. (> Inference)

### Friday 2026-07-24

- [ ] Hold a formal Week 2 decision: validated enough for a sweep, or not validated enough.
- [ ] If validated, define the `3-5` highest-value cases for next week.
- [ ] If not validated, redefine Week 3 around one smaller comparative study and one stronger validation target.
- [ ] Summarize the week's CFD lessons in a reusable note for future teams.

## Week 3: 2026-07-27 to 2026-07-31

Weekly goals:
- [ ] Run a narrow, defensible parameter study.
- [ ] Avoid an unbounded design-space search.
- [ ] Finish the week knowing which `1-2` configurations deserve refinement.

### Monday 2026-07-27

- [ ] Finalize the exact case matrix for the week.
- [ ] Prioritize only the parameters most likely to matter for the chosen rotor family.
- [ ] Make sure each case has a clear reason to exist before you run it.

### Tuesday 2026-07-28

- [ ] Run early cases in the morning and look for obvious failures before launching the full set.
- [ ] Meet with HRI in the afternoon to review whether the chosen sweep is targeted enough.
- [ ] Adjust the case matrix if you are learning that one variable is not worth more time.

### Wednesday 2026-07-29

- [ ] Continue the parameter study.
- [ ] Keep results organized in one comparison table that includes geometry changes, solver notes, and headline outputs.
- [ ] Update the CAD files only when a geometry change is worth preserving, not after every experiment.

### Thursday 2026-07-30

- [ ] Finish the main sweep or get as close as possible without rushing low-quality runs.
- [ ] Rank the cases and identify the top `1-2` candidates.
- [ ] Start drafting the figures and tables that explain the comparison cleanly.

### Friday 2026-07-31

- [ ] Make the Week 3 downselection to the best candidate and one runner-up if needed.
- [ ] Decide what confirmation work is needed next week.
- [ ] Write a short rationale for why the dropped variants are no longer worth time.
- [ ] Update the wiki or a planning note with the stabilized findings.

## Week 4: 2026-08-03 to 2026-08-07

Weekly goals:
- [ ] Confirm the best design choice.
- [ ] Connect the selected design to BOS wind framing and annual-energy estimation.
- [ ] Build report-ready technical figures while the analysis is still fresh.

### Monday 2026-08-03

- [ ] Run the best-case confirmation study at higher fidelity if time and setup credibility allow.
- [ ] Check whether the runner-up still matters or can be retired.
- [ ] Start assembling the final design specification sheet.

### Tuesday 2026-08-04

- [ ] Prepare a concise HRI update showing the selected candidate, the evidence behind it, and the remaining uncertainties.
- [ ] Use the HRI meeting to test whether your interpretation of the results is technically defensible.
- [ ] Capture any requested follow-up runs the same day and triage them immediately.

### Wednesday 2026-08-05

- [ ] Combine the design results with the BOS wind framing.
- [ ] Start the annual-energy estimate using the wind dataset and the performance story you can actually defend.
- [ ] Clearly separate direct results from inference and extrapolation.

### Thursday 2026-08-06

- [ ] Finalize the design decision unless new evidence forces a change.
- [ ] Build the core figures for the report: geometry, CFD setup, validation, parameter comparison, and selected-design performance.
- [ ] Start the report outline with named sections and rough owners.

### Friday 2026-08-07

- [ ] Finish the Week 4 technical package.
- [ ] Review the full evidence chain with your professor: concept choice, validation story, and BOS relevance.
- [ ] Capture one short workflow retrospective on what is now reusable for future teams.

## Week 5: 2026-08-10 to 2026-08-14

Weekly goals:
- [ ] Finish the report and supporting materials.
- [ ] Tighten uncertainty language and make the claims honest.
- [ ] Leave behind a usable record of the design process and the tool workflow.

### Monday 2026-08-10

- [ ] Draft the results and discussion sections.
- [ ] Draft the methods sections for CAD, CFD, and BOS wind framing while the details are still easy to recover.
- [ ] Make a list of every claim that still needs a source, figure, or caveat.

### Tuesday 2026-08-11

- [ ] Prepare the near-final technical story for HRI.
- [ ] Use the HRI meeting to stress-test the report's main conclusions and uncertainty statements.
- [ ] Decide immediately after the meeting what must be revised and what is already solid.

### Wednesday 2026-08-12

- [ ] Revise the report based on HRI and professor feedback.
- [ ] Tighten language around what the simulations show, what they suggest, and what they do not justify.
- [ ] Draft the short AI-tools section, focusing on what materially helped and what still required human judgment.

### Thursday 2026-08-13

- [ ] Finalize the report body, appendices, and figure set.
- [ ] Clean and organize the reusable resources you want to leave behind: prompt log, CFD case log, updated wiki pages, and planning notes.
- [ ] Do one full final read for consistency across claims, numbers, and terminology.

### Friday 2026-08-14

- [ ] Finish final edits and submission packaging.
- [ ] Make sure the final design recommendation, evidence, and uncertainties are all stated plainly.
- [ ] Write a short closing note on what the next team should inherit first.
- [ ] Archive the project state so another team could pick it up without guesswork.

## Guardrails

- If the CFD workflow is still not trustworthy by the end of Week 2, shrink the study instead of pretending the uncertainty is acceptable. (source: sources/HRI2526.md, sources/va10.md, sources/vj11.md)
- If documentation starts taking too much time, keep only the logs that directly support decisions, reproducibility, and handoff. (> Inference)
- If a meeting produces a major decision, update the record the same day rather than relying on memory later. (> Inference)

## Related

- [[Work Plan A1|Work Plan A1]]
- [[CFD and Validation]]
- [[Design Checklist]]
- [[Annual Energy Output]]
