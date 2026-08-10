---
title: Interim Narrative Technical Report Draft
status: draft
reporting_cutoff: 2026-08-03
project: AI-assisted VAWT design workflow
authors: [Anna, Julie]
---

# Designing a Vertical-Axis Wind Turbine While Evaluating an AI-Assisted Engineering Workflow

## Interim Technical Report Draft

**Reporting period:** 22 June 2026 through 3 August 2026  
**Project status:** Active; approximately two weeks remain.  
**Prepared by:** Anna and Julie  
**Review status:** Draft for revision. Replace bracketed placeholders, select approved figures, and confirm external-facing language before submission.

## Abstract

This project has two linked objectives: develop a vertical-axis wind turbine concept for a Boston Logan International Airport context and evaluate how AI tools can support and accelerate an engineering learning and design workflow. The work began with VAWT and fluid-mechanics research, review of a prior HRI project report, and construction of a source-grounded large-language-model wiki. The wiki was designed to preserve source traceability, identify uncertainty, and support evaluation of AI responses rather than accepting fluent output as correct.

The research corpus supported a screening of 63 VAWT designs. After location-specific criteria, independent human scoring, AI-assisted weighted rankings, and sensitivity tests using alternative weighting personas, the team selected two concepts for further exploration: the EN0005 self-start Darrieus concept and the dual-H-rotor hybrid. The original concept ranking placed Darrieus first at 4.40/5 and hybrid second at 4.25/5 under startup- and efficiency-heavy weights; different expert-performance weights reversed that narrow ordering.

AI-assisted CAD tools produced early geometry assemblies very quickly, but later inspection revealed important limitations of the tools. The Darrieus VAWT lacks sufficient published geometry for a full reconstruction and had some unconnected blade-end bodies. The Hybrid is more fully specified but generated models showed disconnected components and, in one Fusion result, an incorrect inner-blade airfoil. Neither model was structurally adequate after just one prompt and supporting pictures, but after some back and fourth, and manual editing the team got the hybrid model CFD-ready.

The CFD work began with NACA0018 airfoil validation attempt at Reynolds number 50,000 and 5 degrees angle of attack which was ultimately unsuccessful due to time constraints. A pseudo-two-dimensional, rounded-trailing-edge case predicted approximately `Cl = 0.57` and `Cd = 0.028-0.030`; which remains below the `Cl = 0.75` AirfoilTools comparison. A NACA0012 control using the same key setup produced `Cl = 0.614` and `Cd = 0.028`, but it can not be used not validate the NACA0018 case. With more time the team would have continued to refine the mesh, and in particular would have focused on the boundary layers. The appropriate conclusion at this stage is that the result is a model-specific prediction requiring a condition-matched benchmark, not a validated aerodynamic coefficient for the final turbine.

## 1. Introduction

### 1.1 Project purpose

The project was framed as a an exercise vertical axis wind turbine design  and as an investigation of practical AI use in engineering. The team did not set out to make an AI driven design of a wind turbine to demonstrate that an AI system could autonomously design a turbine. Instead, the project examined whether a deliberately constrained system could help novice engineers find and organize information, identify knowledge gaps, and learn technical concepts while retaining human control over consequential decisions.

This distinction shaped the work from the outset. The team recognized early on the ways that AI can fail, and built safeguards into the project structure to avoid these pitfalls. The project by tracked four main risks of AI usage: fluency mistaken for correctness, automation bias, anchoring on an initial answer, and sycophancy. The LLM wiki was therefore built with source-only answer rules, citation requirements, explicit labels for unsupported material, and an evaluation loop intended to expose failures.

### 1.2 Scope and reporting boundary

This report covers work completed during an eight week span. It includes research and wiki construction, site and concept selection, CAD experimentation, and the current CFD-validation effort. It does not claim a final VAWT design, a validated turbine power curve, regulatory approval for installation, a completed CFD validation, structural analysis, manufacturing readiness, or measured turbine performance.

## 2. Research and Knowledge-System Stage

### 2.1 Establishing the technical baseline

During the first week, Anna and Julie reviewed fluid-mechanics concepts, a previous capstone report, VAWT literature, and report appendices while meeting with the HRI 99P team. This initial study established the technical vocabulary and identified the need to learn both about VAWT design and the new software workflow before attempting to begin the design phase.

The team also set up OpenCode, Visual Studios, Obsidian, Slack, GitHub, and VS Code Live Share. The early collaboration work included an introductory LLM-wiki workshop, repository creation, shared GitHub access, and asynchronous Git practice. These setup tasks were mandatory project work that help set up the baseline knowledge of the structure of the wiki. The resulting repository was intended to be the shared technical record for research, decisions, CAD, CFD, AI-use lessons, and to organize all the information gathered about VAWTs. 

### 2.2 Building a source-grounded LLM wiki

The team organized the repository so that raw source material was separated from the editable wiki. Broad behavior and quality rules were retained in `AGENTS.md`, while detailed conversion, ingestion, extraction, organization, and maintenance procedures were separated into `schema/` documents. This separation was introduced after early failures made it clear that general instructions did not reliably produce all required steps.

The source-ingestion workflow converted research PDFs to Markdown while attempting to preserve headings, figures, captions, equations, source identifiers, and traceability. Python and PyMuPDF were added to improve image extraction. The team subsequently repaired incorrectly converted files, restored original PDFs that had been removed before the current procedure, corrected unwanted source summarization, repaired image placement and links, and added missing metadata.

The wiki was organized around concepts, methods, designs, and parameters rather than one undifferentiated note per paper. This architecture enabled comparison of design choices such as airfoil, blade count, startup behavior, rated speed, cut-in speed, and power coefficient. Obsidian tags, properties, backlinks, bases, graphs, and Dataview were explored to make relationships among sources and decisions visible.

### 2.3 Reliability findings from the research stage

The wiki became useful for source-grounded retrieval and quiz-based learning, but it did not reliably perform every ingestion task without supervision. Recorded failures included timeouts, missing figures and equations, poor formatting, malformed links, altered source content, incomplete metadata, and difficulty extracting graph-derived values such as `Cp`. The team responded by tightening procedures and manually checking outputs rather than treating the generated pages as automatically correct. The team discovered that using different models lead to variable outputs which were hard to manage. Through creating specific repeatable tasks with instructions pages, like on how to ingest sources or extract figures, these failures significantly decreased in frequency.

This stage established a central project result: information architecture and verification determine whether AI-assisted retrieval is useful. A polished answer, a complete-looking wiki page, or a calculated ranking is not independently valid unless its underlying source evidence and assumptions are checked.

## 3. Site Definition and Design Requirements

### 3.1 Boston Logan context

The team narrowed the open-ended VAWT question to Boston Logan International Airport, focusing on Governor's Island as a preliminary location. Logan was selected because high-resolution wind data were accessible and the location offered a plausible high-energy-demand context with stated decarbonization interest. The report record describes an average wind speed of approximately `5 m/s`; the concept-ranking record uses an average wind speed of `4.8 m/s` and average gusts of `6.3 m/s`. These values should be reconciled against the underlying wind-data analysis before final submission.

Two years of site wind data were added to the wiki and used to produce a wind-speed histogram and guide early design priorities. The team also examined airport airspace regulations and identified Governor's Island as a preliminary candidate area. The `>= 700 ft` runway-edge criterion is a planning note in the design-goal record, not evidence of a confirmed airport installation approval.

### 3.2 Design criteria

The design goal prioritized competitive efficiency, low-speed operation appropriate to the site, manufacturability, minimal maintenance, economic feasibility, airport-regulation compliance, CAD feasibility, and compatibility with good CFD practices within the project timeline.

For concept screening, the team translated these priorities into seven criteria: startup ability with a target of `<= 3 m/s`, efficiency/economics, rated-speed fit around `10-15 m/s`, cut-out-speed fit around `>= 20 m/s`, room for future iteration, CAD/manufacturing feasibility, and team interest. Startup and efficiency each received `35%` of the original weighted score, followed by CAD/manufacturability at `15%`, rated-speed fit at `10%`, and room for growth and cut-out fit at `2.5%` each.

> Uncertainty: The target power, final installation point, site-specific height limit, generator/load curve, and approved airport clearance constraints remain open. The current criteria are suitable for early screening, not a final requirements specification.

## 4. Concept Selection

### 4.1 From 63 designs to a focused candidate set

The research wiki contained 63 VAWT designs when the team began formal screening. Anna and Julie conducted a first pass, with LLM assistance, and identified approximately 8-10 promising concepts each; after comparison, they selected six designs for detailed scoring. The candidates represented straight-bladed H-rotor Darrieus, helical Darrieus, reduced-interference hybrid, Savonius-derived, involute, shifted-troposkien, and other source-specific concepts.

The process deliberately combined independent human scoring with AI-assisted ranking. The LLM was used to retrieve structured evidence, compile comparison tables, and calculate weighted scores. Human scores were retained for qualitative criteria such as team interest and perceived CAD difficulty. The team then varied the criterion weights for beginner, expert, and performance-focused personas to determine whether a narrow result depended on one assumption set.

### 4.2 Ranking result

Under the initial weighting, the self-starting straight-bladed H-rotor Darrieus path ranked first with a weighted score of `4.40/5`, and VJ20 ranked second at `4.25/5`. In the narrower H-type comparison, VA9 ranked first at `4.30/5` and VJ20 second at `4.25/5`. The difference was small enough that the team advanced both concepts instead of treating a single calculated score as a final selection.

The two selected concepts represented a meaningful tradeoff. VA9 offered strong reported low-speed startup evidence, including a reported `1.25 m/s` self-start and `Cp = 0.416`; VJ20 offered a higher reported `Cp` near `0.486`, a reported full-scale cut-in of `2.81 m/s`, and a dual-rotor architecture with more complexity. These values are source-specific design-screening inputs, not predictions for a future Logan installation.

The sensitivity analysis reinforced the decision to keep both designs active. VA9 remained higher under startup-, simplicity-, and beginner-focused weights, while VJ20 ranked higher in the expert BOS-performance scenario, scoring `4.28/5` compared with VA9's `4.13/5`.

### 4.3 A quantitative-AI failure that changed the process

Manual review later found that the LLM had misreported VJ20's cut-in speed during the ranking process. Julie's log records that the original model output cited a `2.9 m/s` value from another design, while a later check of a secondary source reported VJ20's cut-in at `1.5 m/s`; the current worksheet lists the VJ20 full-scale cut-in as `2.81 m/s`. The conflicting values demonstrate that the exact cut-in metric, scale, and source context must be resolved from the primary VJ20 paper before it is used in a final ranking.

The important outcome was not that an AI-derived number was corrected once. It was that the team changed its operating rule: quantitative values, especially those missing from text or presented in figures, require primary-source verification before they influence a consequential design choice.

## 5. CAD Development

### 5.1 Objective and tools

CAD was used as a feasibility test and a preparation stage for later CFD, not as proof of a final turbine design. The team explored Zoo Design Studio and its ZooKeeper agent, including KCL, and later compared Fusion's Autodesk Assistant. The tools were evaluated for their ability to convert research-supported specifications into editable geometry and to support changes without losing traceability.

The team recorded CAD prompts and distinguished source-backed dimensions from inferred support hardware. This record was necessary because a CAD tool can create convincing geometry even when the source does not specify every structural dimension, airfoil coordinate, or connection detail.

### 5.2 VA9 reconstruction

VA9 was difficult to reconstruct faithfully because the paper did not provide complete CAD-ready geometry. The documented source-backed dimensions were a `36.0 cm` blade-body height, `48.0 cm` rotor height, `17.3 cm` rotor radius, and `5.3 cm` chord. The source described a main blade body with two inward-positioned blade ends, but it did not provide a coordinate set for the EN0005 profile, every support dimension, or a definitive blade-end angle.

The team created a parameterized VA9 assembly and iterated primarily on the blade ends. The final logged approximation retained a `46 deg` inward rake and smoother lofted transitions after testing rotated extrusion, trim, loft behavior, intermediate profiles, cup depth, outer-lip width, and a denser profile trace. These are modeling choices for an approximation, not source-validated aerodynamic dimensions.

The VA9 model retains a major limitation: the body and blade ends could not be robustly boolean-unioned after the profile became denser, so they remain touching but separate bodies. Therefore, a visually continuous render should not be interpreted as a watertight solid suitable for manufacture or CFD.

### 5.3 VJ20 reconstruction

VJ20 provided a more complete published rotor specification. The model used two concentric straight-bladed H-rotors on a shared shaft: three outer NACA0018 blades, three inner DU 06-W-200 asymmetric-airfoil blades, `120 deg` spacing within each three-blade rotor, and a `60 deg` phase offset between the rotors. The prompts prohibited unreported features such as a Savonius rotor, helicity, taper, variable pitch, shrouds, and guide vanes; support hardware was intentionally labeled as inferred and editable.

ZooKeeper generated complex initial assemblies rapidly, but tool-level success did not guarantee usable geometry. The team observed disconnected blades, floating blocks around inner blades, a missing inner top strut after a repair, incorrect inner brackets, and instability when changing rotor azimuth. Reading KCL and asking the agent to identify modified code lines improved the team's ability to inspect and repair the model, but did not eliminate the need for independent CAD expertise.

Fusion generated full-scale and `1/11.01` scaled VJ20 models more quickly than ZooKeeper in one trial. Later inspection found that the Fusion inner blades did not use the required DU 06-W-200 asymmetric airfoil. The model is therefore a useful visual and CFD-planning starting point, not a source-faithful VJ20 reproduction.

### 5.4 CAD result

The CAD work showed that AI can accelerate first-pass parametric geometry, but it also made visual inspection, source traceability, and manual model understanding more important. VA9 remains useful as a parameterized approximation with unresolved source geometry and multi-body issues. VJ20 remains the more tractable baseline because more source geometry is available, but its inner-airfoil fidelity, connections, watertightness, and CFD-specific simplification still require verification.

## 6. CFD Setup and Airfoil Validation

### 6.1 Purpose of the validation study

Before using CFD to compare VAWT designs, the team attempted to establish a defensible airfoil workflow. The active study uses a NACA0018 airfoil at `Re = 50,000`, `5 deg` angle of attack, `1.0 m` chord, inlet velocity `0.7645 m/s`, and air density `1.196 kg/m3`. The early comparison target was an AirfoilTools curve, approximately `Cl = 0.75` at the stated condition.

The common later setup was an incompressible, steady-state `k-omega SST` case with a velocity inlet, pressure outlet, slip outer boundaries, no-slip airfoil walls, and lift and drag coefficients defined along `+y` and `+x`, respectively. The study was repeatedly revised as the team learned about finite-span effects, pseudo-two-dimensional modeling, coefficient reference area, boundary layers, `y+`, mesh quality, non-orthogonality, and trailing-edge geometry.

### 6.2 Key experimental sequence

The first batch used several external-flow domains and mesh choices. NACA0018 predictions ranged from `Cl = 0.1306` to `0.261` and `Cd = 0.0397` to `0.061`, substantially below the lift comparison value. One early pseudo-two-dimensional run produced no usable results because result controls had not been configured. These outcomes were exploratory and did not provide a validation basis.

The team then identified a comparability problem: an initial finite-span, three-dimensional airfoil case cannot be directly compared with two-dimensional sectional data. Reducing the spanwise flow volume to `0.5 m` and correcting the reference area from `1 m2` to `0.5 m2` changed the recorded NACA0018 result from `Cl = 0.291`, `Cd = 0.026` with the inconsistent area to `Cl = 0.583`, `Cd = 0.052` with the corrected area. The change illustrates that coefficient normalization and dimensionality are part of the physical setup, not postprocessing details.

Mesh and near-wall tests then altered mesh fineness, first-layer thickness, wall treatment, turbulence intensity, non-orthogonal correctors, and the trailing-edge geometry. Increasing fineness to `8` produced `Cl = 0.515`, `Cd = 0.041`. Rounding the trailing edge, using a `0.00001 m` first layer, and applying two non-orthogonal correctors produced a lower maximum `y+` of `4.913` with `Cl = 0.570` and `Cd = 0.028`; increasing fineness to `7` produced `Cl = 0.572` and `Cd = 0.030`.

### 6.3 Control cases and interpretation

Using the same key rounded-tail setup, the NACA0012 control produced `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`. Direct STEP inspection confirmed approximately `1 m` chord, nominal `12%` and `18%` thicknesses for the NACA0012 and NACA0018 geometries, and a `0.5 m2` reference area for the retained pseudo-two-dimensional wetted section.

The NACA0012 control supports the conclusion that no currently observed shared domain, reference-area, orientation, scale, or rounded-tail-CAD issue explains the NACA0018 discrepancy. It does not prove the NACA0018 AirfoilTools comparison is incorrect, validate the rounded NACA0018 as an ideal sharp profile, establish mesh independence, or validate a VAWT CFD workflow.

The literature record also identifies a low-turbulence NACA0018 experiment with different low-Reynolds-number behavior, including `Clmax = 0.435` at `Re = 50,000` and `3 deg`. This means AirfoilTools is not the only relevant reference context, and the remaining discrepancy cannot be assigned confidently to one solver setting.

### 6.4 Current CFD status

The best documented NACA0018 result is approximately `Cl = 0.57` and `Cd = 0.028-0.030` for a steady, `k-omega SST`, rounded-NACA0018 pseudo-two-dimensional SimScale case. It should be reported exactly as that model-specific prediction, not as an experimentally validated coefficient.

Later mesh refinement work improved mesh appearance and varied boundary-layer count, overall thickness, growth rate, surface sizing, volume refinements, and local refinement placement. Results remained inconsistent, and the current record includes residual, non-orthogonality, and reference-benchmark concerns. The team has appropriately shifted from attempting to force agreement with one target toward documenting the case and seeking a condition-matched benchmark and expert review.

## 7. Assessment of AI in the Workflow

### 7.1 High-value uses

The strongest observed AI uses were retrieval across a curated source set, organization of research into comparable notes, generation of candidate work plans, calculation of weighted decision scores, initial CAD generation, and guided learning through explanations and quizzes. These uses accelerated the movement from a broad literature collection to a structured design conversation.

The design-selection workflow demonstrates the benefit concretely. AI made repeated ranking and sensitivity scenarios practical, while human-defined criteria and independent scores preserved a way to inspect the result. CAD tools similarly made it possible to produce and compare complex initial assemblies before the team could have modeled them conventionally at the same level of detail.

### 7.2 Limits and failures

The weakest observed uses were unsupervised quantitative extraction, reliable source conversion and formatting, tracking the full state of repeated CFD iterations, and autonomous technical troubleshooting. The VJ20 cut-in-speed misreport, malformed conversions, missing figures, wrong CAD airfoil, disconnected geometry, and repetitive CFD advice are evidence that AI output must be treated as a proposal for review rather than a completed engineering task.

The project also surfaced a learning tradeoff. Fast synthesis can reduce the time spent engaging directly with papers and struggling through technical concepts, which may reduce deep understanding. The team responded by using the wiki as a teaching tool, asking it to quiz and explain concepts, reviewing source documents, and preserving records of assumptions and failures.

### 7.3 Interim workflow principle

The evidence supports a human-led workflow: use AI to broaden search, organize information, expose alternatives, perform transparent calculations, and create first-pass artifacts; use humans to define the objective, judge source quality, verify numbers, inspect geometry, choose acceptable tradeoffs, and decide when a result is sufficiently validated.

## 8. Conclusions and Remaining Work

By 3 August, the project had completed a substantial research and screening phase, built a source-grounded technical knowledge system, selected VA9 and VJ20 as leading concepts, generated exploratory CAD models, and created a detailed record of an incomplete airfoil CFD-validation effort. The work has not yet produced a validated final VAWT, but it has established a traceable foundation for the remaining design and validation tasks.

The next two weeks should prioritize the smallest set of actions that produce defensible evidence: verify the baseline CAD geometry and its CFD suitability, resolve the CFD benchmark and mesh-quality acceptance criteria, run only staged simulations whose controls and outputs are confirmed, and document the final AI-workflow lessons from both successes and failures.

> Uncertain: The final VAWT geometry, airport installation feasibility, full-turbine CFD results, aerodynamic performance, and manufacturing feasibility are not established by the current record.
>
> Check next: Confirm source-level VJ20 operating values; select a matched NACA0018 benchmark; verify CAD watertightness, airfoil identity, and face groups; define CFD mesh, convergence, timestep, and periodicity acceptance criteria before interpreting a turbine result.

---

# Appendix A. Project Timeline Through 3 August 2026

| Period | Major completed work | Evidence |
| --- | --- | --- |
| Week 1, 22-26 June | Reviewed fluid mechanics, previous report, VAWT research, and project references; set up OpenCode, VS Code, Obsidian, Slack, GitHub, and Live Share; began LLM-wiki workshop, source ingestion, evals, and shared repository workflow. | active/_anna daily log.md; active/_Julie_daily_log.md |
| Week 2, 29 June-3 July | Repaired source conversions; added Python/PyMuPDF-assisted image extraction; created `schema/` procedures; improved metadata, links, figures, equations, wiki organization, design pages, and parameter pages. | active/_anna daily log.md; active/_Julie_daily_log.md |
| Week 3, 6-10 July | Evaluated Boston wind data and Logan siting; created design goal and work plan; screened and ranked designs; selected VA9 and VJ20 for further study; began Zoo/ZooKeeper CAD exploration. | active/_anna daily log.md; active/_Julie_daily_log.md; active/analysis/Concept ranking worksheet.md |
| Week 4, 13-17 July | Learned SimScale and CFD fundamentals; began NACA0018 validation; added SimScale and targeted CFD sources; explored pseudo-two-dimensional setup, reference area, mesh refinement, `y+`, and control cases. | active/_anna daily log.md; active/_Julie_daily_log.md; active/documentation/CFD log/Airfoil Validation Studies.md |
| Week 5, 20-24 July | Continued airfoil validation and mesh troubleshooting; created full-scale and scaled VJ20 CAD; attempted VJ20 CFD setup; identified the VJ20 cut-in reporting issue; met with Ryan and Philip for workflow and CFD guidance. | active/_anna daily log.md; active/_Julie_daily_log.md |
| Week 6, 27-31 July | Continued mesh refinement with expert feedback; installed COMSOL as a possible fallback; inspected geometry defects affecting mesh quality; began full-turbine setup while continuing reporting and documentation. | active/_anna daily log.md; active/_Julie_daily_log.md |
| Week 7, 3 August | Continued SimScale work after geometry cleanup and added documentation images; two remaining weeks were still planned at the reporting cutoff. | active/_Julie_daily_log.md |

# Appendix B. Concept-Selection Evidence Snapshot

| Item | Recorded value or outcome | Interpretation limit |
| --- | --- | --- |
| Design corpus | `63` VAWT designs in the wiki | Count supports scope of screening, not equal evidence quality for every design. |
| Detailed concepts | `6` designs after the initial human/LLM pass | The initial shortlist contained human judgment and may not be exhaustive. |
| Initial ranking weights | Startup `35%`; efficiency `35%`; CAD/manufacturability `15%`; rated-speed fit `10%`; growth `2.5%`; cut-out fit `2.5%` | Weights represent project priorities, not universal VAWT optimization weights. |
| VA9 result | `4.40/5` in original weighted table; reported `1.25 m/s` self-start; reported `Cp = 0.416` | Source-specific evidence; not a Logan performance prediction. |
| VJ20 result | `4.25/5` in original weighted table; reported `Cp = 0.486`; reported `2.81 m/s` full-scale cut-in | Cut-in records conflict across project notes and require primary-source reconciliation. |
| Sensitivity result | VA9 stronger under practicality/startup weightings; VJ20 stronger under expert-performance weighting (`4.28/5` vs `4.13/5`) | Supports advancing both concepts, not declaring one universal winner. |

# Appendix C. CAD Geometry Ledger

| Concept | Source-backed geometry carried into CAD | Inferred or unresolved geometry | Current limitation |
| --- | --- | --- | --- |
| VA9 EN0005 self-start Darrieus | `36.0 cm` blade-body height; `48.0 cm` rotor height; `17.3 cm` rotor radius; `5.3 cm` chord; main body plus inward blade ends | EN0005 coordinates, support dimensions, definitive blade-end angle, and full structural design | Blade body and ends remain separate touching bodies after boolean-union failure; model is an approximation. |
| VJ20 dual H-rotor hybrid | Three outer NACA0018 blades; three inner DU 06-W-200 blades; `120 deg` blade spacing; `60 deg` rotor phase offset | Hubs, struts, bearings, generator mount, and other mechanical details | Zoo models showed disconnected/floating components; Fusion inner blades did not match the required asymmetric airfoil. |

# Appendix D. Airfoil CFD Validation Record

## D.1 Case definition

| Parameter | Value |
| --- | --- |
| Airfoil | NACA0018 |
| Angle of attack | `5 deg` |
| Reynolds number | `50,000` |
| Chord | `1.0 m` |
| Inlet velocity | `0.7645 m/s` |
| Air density | `1.196 kg/m3` |
| Primary model | Incompressible, steady-state `k-omega SST` |
| Pseudo-2D reference area | `0.5 m2` for `1.0 m` chord and `0.5 m` wetted span |

## D.2 Selected results

| Case | Key change | `Cl` | `Cd` | Note |
| --- | --- | ---: | ---: | --- |
| Batch 1 Runs 1-5 | Early domains and meshes | `0.1306-0.261` | `0.0397-0.061` | Exploratory cases; inadequate validation basis. |
| Batch 2 Run 5 | Pseudo-2D span and corrected `0.5 m2` area | `0.583` | `0.052` | Area correction materially changed reported coefficient. |
| Run 8 | Mesh fineness `8` | `0.515` | `0.041` | Improved drag but lower lift. |
| Run 13 | Rounded tail, near-wall changes, two non-orthogonal correctors | `0.570` | `0.028` | Maximum `y+ = 4.913`; best documented low-drag case. |
| Run 14 | Run 13 with fineness `7` | `0.572` | `0.030` | Result effectively unchanged. |
| Run 15 control | NACA0012 with Run 13 settings | `0.614` | `0.028` | Supports the shared workflow but does not validate NACA0018. |

## D.3 CFD limitations to retain in final report

- No complete mesh-independence, domain-independence, convergence, transition-model, or cycle-repeatability study has been documented.
- The rounded NACA0018 geometry is not an ideal sharp trailing-edge NACA0018 and cannot be treated as an exact match to every external reference.
- AirfoilTools and the low-Reynolds-number `cj9` experiment represent different reference contexts; neither alone closes the validation question.
- The NACA0010 supplementary drag value is recorded as `0.27` while also described as correct; it should be checked against the saved SimScale output before inclusion in any final report.

# Appendix E. Recommended Figures and Evidence to Insert

1. A project workflow diagram: research sources -> conversion and procedures -> wiki -> site/design criteria -> ranking -> CAD -> CFD -> human verification. Use a newly created diagram rather than implying automation alone made decisions.
2. A Logan wind-speed histogram with its data period, station, units, and processing method stated in the caption. Do not use an unlabeled screenshot.
3. The concept ranking table with weights and explicit uncertainty labels for inferred or missing data.
4. A VA9 render beside an annotation of source-backed versus inferred geometry.
5. A VJ20 render with blade-count, rotor-phase, and airfoil-verification status identified.
6. A CFD mesh and coefficient-history figure that identifies the exact run, geometry, mesh settings, reference area, and convergence status.

# Appendix F. Source Records Used for This Draft

- `active/_anna daily log.md`
- `active/_Julie_daily_log.md`
- `active/analysis/Design goal.md`
- `active/analysis/Decision Making Process.md`
- `active/analysis/Concept ranking worksheet.md`
- `active/documentation/Anna blog + report writing.md`
- `active/documentation/CAD Modeling Process Blog Post.md`
- `active/documentation/CFD log/Airfoil Validation Studies.md`
- `active/documentation/CFD log/Airfoil Validation Study Summary and Report Outline.md`
- `active/documentation/Weeks 1-4 Project Summary and Report Outline.md`
- `sources/cj9.md`

# Appendix G. Boston Logan Location Selection and Wind Analysis

## G.1 Purpose and site-selection basis

The project required a specific urban or suburban context so that VAWT design choices could be screened against an actual wind record rather than against a generic wind-speed assumption. Boston Logan International Airport (BOS) was selected from the Boston-area locations considered because station data were available at high temporal resolution over multiple years and the airport provided a plausible high-energy-demand, decarbonization-relevant use context. The intended use of the location was early design screening, not a claim that a turbine has been approved for installation.

Governor's Island was identified as a preliminary perimeter-area candidate because it is separated from the central runway field and exposed to the bay on two sides. The project design-goal note records a planning target of at least `700 ft` from a runway edge. That distance is a preliminary screening assumption, not a surveyed clearance, FAA determination, Massport approval, or confirmation that a turbine can be installed at that location.

## G.2 Airport-airspace screening

Airport construction is subject to FAA notice and obstruction-review requirements. Under 14 CFR Part 77, notice is required for construction taller than `200 ft` above ground level and for shorter construction that exceeds the relevant imaginary surface. The applicable civil-airport surfaces include horizontal, conical, primary, approach, and transitional surfaces. The primary surface may be up to `1,000 ft` wide for precision and some non-precision instrument runways; approach surfaces can rise at `20:1`, `34:1`, or `50:1`; and transitional surfaces rise at `7:1` from the sides of the primary and approach surfaces.

These regulations support treating outer side-perimeter areas as more plausible preliminary candidates than locations between runways or directly beyond runway ends. They do not establish an allowable height at Governor's Island. A site-specific conclusion would require an airport layout and runway-approach information, a surveyed turbine position and ground elevation, the proposed turbine height, and an FAA obstruction evaluation. Any final siting decision would also require approval from the airport owner and other applicable authorities.

## G.3 Wind-data record and processing

Wind records were obtained for station `BOS` (`BOSTON/LOGAN INTL`) through the Iowa Environmental Mesonet ASOS request interface. The project record identifies the measurement height as approximately `9 m` above ground. The processed one-year table contains hourly UTC observations with wind speed, direction, gust direction, and gust speed. Wind and gust values were converted from knots to metres per second using `1 knot = 0.514444 m/s`.

Two distributions were retained for different purposes:

| Dataset | Period | Intended use | Limitation |
| --- | --- | --- | --- |
| One-year BOS record | July 2025 to July 2026 | Early site characterization and initial histogram | Significant gaps leave approximately `73%` of the year represented. |
| Five-year BOS record | July 2021 to July 2026 | Annual-energy-oriented distribution and broader design screening | The station record is not a measurement at the proposed Governor's Island installation point. |

The histograms use `0.5 m/s` wind-speed bins from `0` to `18 m/s` and plot the share of observations in each bin. The one-year and five-year histogram files are retained with the data so that the distribution can be inspected instead of relying only on a mean wind speed. Observations above `18 m/s` are not shown as separate histogram bins in the five-year rendering.

## G.4 Results used in concept screening

The early design record reports an average BOS wind speed of `4.8 m/s` and average gusts of `6.3 m/s`. A separate narrative description rounds the mean wind speed to approximately `5 m/s`; these are treated as the same preliminary characterization rather than independent site measurements. The distribution was used to emphasize designs capable of low-speed startup, while retaining rated-speed, efficiency, structural, manufacturing, maintenance, and airport-constraint considerations. It did not provide a turbine power curve, annual energy production estimate, or proof that a particular VAWT will perform at BOS.

The main wind-analysis limitation is representativeness. The available observations describe the BOS weather-station record at approximately `9 m`, whereas the final turbine location, height, surface roughness, local obstructions, turbulence intensity, and wind-direction effects remain unspecified. Because wind power varies with the cube of velocity, even a modest mismatch between the station and installed conditions could materially change energy predictions. Site-specific anemometry at the selected installation point, supplemented by a completeness check and a documented treatment of missing data, is required before using the distribution for final annual-energy or economic conclusions.

## G.5 Evidence and remaining work

| Evidence item | Role in this project | What it does not establish |
| --- | --- | --- |
| BOS station wind records and histograms | Establishes an accessible, multi-year reference distribution for early design screening | Wind conditions at the final turbine position or annual energy production |
| `4.8 m/s` mean wind and `6.3 m/s` mean gust values | Frames the site as a low-to-moderate-wind design context | A universal VAWT operating target or guaranteed performance |
| Governor's Island perimeter concept | Provides a preliminary location for discussing installation constraints | A confirmed parcel, turbine footprint, permitted height, or approval |
| 14 CFR Part 77 review | Identifies the need to evaluate airport imaginary surfaces and obstruction requirements | An FAA determination or authorization to construct |

Before a design is presented as site-specific, the project should reconcile the precise analysis period and the reported wind summary, identify a surveyed candidate point, measure wind speed and direction at the intended hub height, complete a site-specific obstruction review, and combine the resulting wind distribution with a validated turbine power curve and generator/load model.

**Appendix G source records:** `active/analysis/Design goal.md`; `active/analysis/brainstorm.md`; `attachments/wind data/BOS_07.25_to_07.26.md`; `attachments/wind data/BOS_07.21_to_07.26.json`; `attachments/wind data/BOS_07.25_to_07.26_histogram.svg`; `attachments/wind data/BOS_07.21_to_07.26_histogram.svg`; `active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md`; `wiki/concepts/Airport Regulations.md`; `wiki/log.md`.

# Appendix H. Concept-Selection Process and Ranking Record

## H.1 Purpose and decision method

The concept-selection process narrowed a broad VAWT research corpus into a small set of designs suitable for further CAD exploration. The selection was intentionally site-informed: the BOS reference record indicated a low-to-moderate wind context, and the preliminary airport setting added constraints related to maintainability, manufacturability, height, and regulatory feasibility. The resulting process combined source-grounded wiki retrieval, independent human scoring, AI-assisted score calculation, and sensitivity analysis through alternative weighting schemes.

Scores in the initial worksheet use a `1-5` scale, where `5` is best relative to that candidate set. An asterisk in the original worksheet marks an informed estimate made when the source did not provide a direct metric or when the row described a broader concept family rather than one tested turbine. The scores therefore support comparative early screening, not a validated prediction of BOS energy production or a final design choice.

## H.2 Selection criteria

| Criterion | Why it was selected | Best or target value used in screening |
| --- | --- | --- |
| Startup ability | BOS wind conditions made the ability to begin rotating in low wind especially important; a design that cannot start frequently cannot use much of the available resource. | Cut-in or self-start at or below `3 m/s`. |
| Efficiency / economics | A VAWT needed sufficient aerodynamic efficiency and energy capture to have a plausible path toward economic value. | Highest credible `Cp` or strongest efficiency evidence, while recognizing that `Cp` alone does not establish economics. |
| Rated-speed fit | The rated-speed target was used to favor designs whose reported operating range was compatible with the project design brief. | Approximately `10-15 m/s`. |
| Cut-out-speed fit | The design needed a credible high-wind operating or survival limit rather than only low-wind performance. | At least `20 m/s`. |
| Room for growth | The project required a baseline that could support later parameter studies rather than a geometry with no practical tuning variables. | Clearly identifiable, plausible parameters for further modeling and optimization. |
| CAD + manufacturability | The team needed a concept that could be represented in the available CAD tools and could plausibly be fabricated without unnecessary complexity. | Simple, editable, and feasible geometry relative to the project timeline and available tools. |
| Interest to the team | The team included this qualitative criterion to retain ownership of the exploratory project direction. | Highest interest score; this criterion was not included in the weighted numerical total. |

The first six criteria were used in the weighted score. Startup and efficiency initially received the greatest weight because the team judged low-wind use and economic performance to be the dominant BOS design concerns. Interest was recorded but deliberately excluded from the calculated total so that a preferred concept could not win solely because it was appealing to pursue.

## H.3 Initial screening and eight-candidate comparison

The daily logs show that the team first used Boston wind data and airport constraints to make the problem specific, then developed the selection categories and weights together. Anna and Julie independently reviewed candidates before asking the LLM to repeat the ranking and calculate the weighted totals. The early process also used a narrower H-type comparison and a broader all-design search so that an initially attractive family would not be accepted without checking alternatives.

The eight concepts below were the documented initial recommendation and non-traditional candidate set. They include both concept families and specific source-backed designs, so this table is an early concept screen rather than a uniform comparison of eight identical prototypes.

| Candidate | Screening rationale | Primary caution |
| --- | --- | --- |
| Self-starting straight-bladed H-rotor Darrieus | Strong low-wind path: VA9 reported `1.25 m/s` self-start and `Cp = 0.416`; the straight H-rotor form also offered a relatively clean modeling and iteration path. | Darrieus startup is a broader risk; the claimed benefit depends on the EN0005 blade and blade-end behavior carrying into the modeled design. |
| Low-TSR helical Darrieus | Offered smoother torque, lower cyclic loading, and an urban-oriented architecture; the cited example reported `3.5 m/s` startup and `100 W` at `9 m/s`. | More difficult to model and manufacture, and the strongest cited rated condition was below the target band. |
| Reduced-interference hybrid | Offered a possible startup-efficiency compromise; VJ20 reported `Cp = 0.486`, while another hybrid source reported a torque benefit from relocating the Savonius rotor. | Greater aerodynamic and structural complexity, with source-dependent startup and scaling claims. |
| Compact drag-based J-type / Savonius-derived fallback | Retained as a simple, self-starting, low-wind fallback; the J-type example reported `3 m/s` cut-in and easy installation and maintenance. | Lower peak-efficiency potential than the leading lift-based concepts. |
| Involute rotor with wind-flow modifier | The modifier-assisted case reported `Cp = 0.397` at `5 m/s`, making it relevant to low-wind BOS screening. | The CFD-heavy evidence and directional rectangular modifier conflict with the desired omnidirectional use case. |
| VJ20 proposed hybrid VAWT | Combined high reported `Cp` (`0.486` at `TSR = 3`), self-starting behavior, and a listed `2.81 m/s` full-scale cut-in. | It was more complex than a simple H-rotor and its reported startup values varied by scale and source context. |
| 50% STS-VAWT | Offered a reported corrected `Cp` improvement of approximately `10%` by reducing blade-wake interaction. | It was supported as a wake-management and efficiency concept, not as a low-speed startup solution. |
| Scooplet-based Savonius | Offered simple manufacture from straight lines and circular arcs, with a reported `39%` `Cp` improvement over a classical Savonius reference. | It remained a drag-rotor concept with a lower expected efficiency ceiling than the top lift-based candidates. |

The original six-row ranking table retained six representative candidates for detailed scoring: self-starting straight-bladed H-rotor Darrieus, low-TSR helical Darrieus, involute rotor with wind-flow modifier, VJ20, 50% STS-VAWT, and scooplet Savonius. Under the original weighting, the self-starting H-rotor scored first at `4.40/5`, followed by VJ20 at `4.25/5`. The small difference led the team to retain both directions for further reading and CAD exploration instead of declaring one final winner.

## H.4 Weighting schemes and persona rationale

The sensitivity analysis tested whether the outcome depended on the initial priorities. The original weighting emphasized the project brief as initially framed. The BOS-focused weighting redistributed some emphasis toward rated-speed fit and iterative potential. The beginner-friendly weighting represented a team with limited CAD and simulation experience, so it prioritized feasibility and modelability. The expert-performance weighting assumed strong CAD and CFD capability, allowing more emphasis on operating performance and optimization potential than on simple fabrication.

| Weighting scheme | Startup | Efficiency / economics | Rated-speed fit | Cut-out-speed fit | Room for growth / modelability | CAD + manufacturability | Rationale |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | --- |
| Original performance-first concept weighting | `35%` | `35%` | `10%` | `2.5%` | `2.5%` | `15%` | Represents the initial priority on low-wind startup and efficiency, while retaining a practical CAD/manufacturing constraint. |
| BOS-focused all-design weighting | `30%` | `25%` | `15%` | `5%` | `10%` | `15%` | Represents a site-specific screening view that gives more credit to operating-speed fit and the ability to refine a design. |
| Beginner-friendly all-design weighting | `20%` | `15%` | `5%` | `5%` | `25%` | `30%` | Represents a novice team whose main constraint is finishing a credible, editable, manufacturable design. |
| Expert BOS-performance weighting | `20%` | `25%` | `20%` | `10%` | `20%` | `5%` | Represents an expert team seeking the best BOS-specific performance and willing to accept greater CAD and manufacturing complexity. |

## H.5 Persona results: top six designs in each full-corpus screen

The worksheet reports three persona-based rankings across the broader design corpus. The table below preserves the top six from each view. These are separate rankings, not a direct claim that every design had equally complete underlying data. In particular, the worksheet notes that missing startup, rated-speed, or cut-out values make lower-ranked positions less stable.

| Rank | BOS-focused design | Score | Beginner-friendly design | Score | Expert BOS-performance design | Score |
| --- | --- | ---: | --- | ---: | --- | ---: |
| 1 | VA9 EN0005 self-start Darrieus | `4.30` | VA9 EN0005 self-start Darrieus | `4.45` | VJ20 proposed hybrid VAWT | `4.28` |
| 2 | VJ20 proposed hybrid VAWT | `4.15` | VJ20 proposed hybrid VAWT | `4.15` | VA9 EN0005 self-start Darrieus | `4.13` |
| 3 | VJ25 1-kW twin-bladed H-rotor, `AR = 0.4` | `3.60` | VA5 J-type VAWT | `4.00` | VJ25 1-kW twin-bladed H-rotor, `AR = 0.4` | `4.00` |
| 4 | VA3 Solwind vertical-axis wind turbine | `3.45` | VJ19 curved-blade Savonius VAWT | `3.90` | VJ25 1-kW twin-bladed H-rotor, `AR = 2` | `3.95` |
| 5 | VJ25 1-kW twin-bladed H-rotor, `AR = 2` | `3.40` | VJ25 1-kW twin-bladed H-rotor, `AR = 0.4` | `3.80` | VA3 Solwind vertical-axis wind turbine | `3.80` |
| 6 | VJ19 curved-blade Savonius VAWT | `3.35` | VA26 3-bladed H-type VAWT | `3.70` | VA24 variable-pitch 3-bladed NACA0015 VAWT | `3.72` |

Across all weighting schemes, VA9 and VJ20 occupied the top two positions. VA9 was favored when startup, simplicity, and practical robustness were emphasized. VJ20 moved ahead only in the expert-performance case, where efficiency, rated-speed fit, and optimization room outweighed CAD simplicity. This result justified advancing both concepts into CAD rather than treating the score as a definitive selection.

## H.6 Full-wiki BOS-focused ranking: top ten of 63 designs

After the initial screen, the ranking process was applied to the broader 63-design wiki set using the BOS-focused weighting. Duplicate real machines were collapsed so that the same turbine did not fill multiple ranks. The table reports the top ten results from that full-corpus screening.

| Rank | Design | Score (/5) | Recorded reason for position |
| --- | --- | ---: | --- |
| 1 | VA9 EN0005 self-start Darrieus | `4.30` | Reported `1.25 m/s` self-start, `Cp = 0.416`, and stability at `25 m/s`. |
| 2 | VJ20 proposed hybrid VAWT | `4.15` | Reported `Cp = 0.486`, explicit self-starting, and `2.81 m/s` full-scale cut-in. |
| 3 | VJ25 1-kW twin-bladed H-rotor, `AR = 0.4` | `3.60` | Reported `cpmax = 0.475`, explicit `10 m/s` design point, and a strong modeling baseline. |
| 4 | VA3 Solwind vertical-axis wind turbine | `3.45` | Reported `1.5 m/s` startup, `3.7 m/s` power onset, `10 m/s` rated output, and slowdown around `27 m/s`. |
| 5 | VJ25 1-kW twin-bladed H-rotor, `AR = 2` | `3.40` | Reported `cpmax = 0.464` and a `10 m/s` design point. |
| 6 | VJ19 curved-blade Savonius VAWT | `3.35` | Reported `3 m/s` cut-in, `9 m/s` rated-speed claim, and `3.5 year` simple payback. |
| 7 | VA3 Ropatec WRE.060 WindRotor | `3.35` | Reported `2 m/s` cut-in, `14 m/s` rated speed, and hybrid low-speed intent. |
| 8 | VA24 variable-pitch 3-bladed NACA0015 VAWT | `3.10` | Reported `Cp = 0.568` peak and improved low-TSR behavior, offset by active-pitch complexity and incomplete whole-turbine operating data. |
| 9 | VA26 3-bladed H-type VAWT | `3.10` | Simple fixed-pitch layout, `7 m/s` operating case, and clear parameter-tuning opportunities. |
| 10 | VA5 J-type VAWT | `3.00` | Reported `3 m/s` cut-in, `23.3%` prototype efficiency, and simple fabrication and maintenance. |

Several trends emerged. Straight-bladed H-rotor or Darrieus-derived designs dominated the top positions because they combined low-speed evidence, relatively high reported `Cp`, and clear optimization variables. The VJ25 aspect-ratio pair also ranked highly, indicating that a simple H-rotor can remain attractive when a study supplies a clear operating point and parameterized geometry. Drag-based designs remained competitive when their startup, fabrication, or operating data were unusually complete, but their efficiency ceiling generally limited their rank. The variable-pitch design rose despite its complexity because the expert and BOS-oriented views recognized its high reported performance and potential for further optimization.

## H.7 Limits and decision outcome

The ranking was a structured design-screening tool, not a final validation exercise. It mixed concept families with individual designs, relied in part on informed estimates when sources omitted data, and contained a later-identified VJ20 cut-in-speed reporting conflict. The daily logs document that the team recognized this risk: AI accelerated comparison but could infer values not directly supported by a source, which would make a numerical ranking appear more certain than it was. The team therefore used the results to identify VA9 and VJ20 as two leading directions for CAD feasibility testing, not to claim that either was already the best turbine for BOS.

**Appendix H source records:** `active/_anna daily log.md`; `active/_Julie_daily_log.md`; `active/analysis/Concept ranking worksheet.md`; `active/analysis/Decision Making Process.md`; `active/analysis/brainstorm.md`; `active/analysis/Design goal.md`.
