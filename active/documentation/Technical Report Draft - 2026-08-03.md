---
title: Interim Technical Report Draft
status: draft
reporting_period: 2026-06-22 through 2026-08-14
project: AI-assisted VAWT design workflow
authors: [Anna, Julie]
---

# Designing a Vertical-Axis Wind Turbine While Evaluating an AI-Assisted Engineering Workflow

## Interim Technical Report Draft

**Reporting period:** 22 June 2026 through 14 August 2026<br>
**Project status:** Active; approximately one week remains.<br>
**Prepared by:** Anna and Julie  
**Review status:** Draft for revision. Replace bracketed placeholders, select approved figures, and confirm external-facing language before submission.

## Abstract

This project had two linked objectives: develop a vertical-axis wind turbine concept for a Boston Logan International Airport context and evaluate how AI tools can support and accelerate an engineering learning and design workflow. The work began with broad research into vertical-axis wind turbines (VAWTs) and the construction of a large-language-model (LLM) wiki. The wiki was designed to store, organize, and retrieve information in order to facilitate the team’s learning and design work.

After BOS-specific criteria were developed, an agent-assisted concept-selection process was completed to identify the VAWT design or concept most suitable for BOS and further optimization. This process consisted of independent human scoring, agent-assisted weighted rankings, and sensitivity tests using alternative weighting personas. Two concepts were selected for further exploration: the EN0005 self-start Darrieus concept and the dual-H-rotor hybrid. The original concept ranking placed Darrieus first at 4.40/5 and the hybrid second at 4.25/5 under startup- and efficiency-heavy weights; different expert-performance weights reversed that narrow ordering.

AI-assisted CAD tools produced early geometry assemblies very quickly, but later inspection revealed important limitations of the tools and models that required manual fine-tuning. The Darrieus VAWT lacked sufficient published geometry for a full reconstruction. The hybrid was more fully dimensioned, but generated models initially showed discrepancies, including an incorrect inner-blade airfoil. Neither model was structurally adequate after one prompt and supporting pictures; after iterative prompting and manual editing, the hybrid model became suitable for CFD preparation.

CFD simulations began with a NACA 0018 airfoil validation attempt at Reynolds number 50,000 and 5 degrees angle of attack, which was ultimately unsuccessful because of time constraints. A pseudo-two-dimensional, rounded-trailing-edge case predicted approximately `Cl = 0.57` and `Cd = 0.028-0.030`, which remains below the `Cl = 0.75` AirfoilTools comparison. A NACA0012 control using the same key setup produced values matching the AirfoilTools data, but high non-orthogonality made the result unreliable. Significant time was spent preparing a simulation and acceptable mesh for CFD analysis of the dual-H-rotor hybrid VAWT; a validated full-turbine result had not been obtained at the reporting cutoff.

## 1. Introduction

### 1.1 Project purpose

The primary goal of this project was to explore and evaluate the utility of novel artificial intelligence (AI) tools in the context of an engineering design project. The initial goal of the engineering project was to design a vertical-axis wind turbine (VAWT) for a Boston Logan Airport application; however, because of time constraints, the scope was abridged to target a VAWT CFD simulation that matched literature data.

Vertical-axis wind turbines are an underdeveloped renewable-energy technology that is particularly promising for capitalizing on wind power in urban environments because they can function in multidirectional and turbulent wind conditions. Renewable and distributed energy sources such as VAWTs could reduce strain on the centralized U.S. energy system and reduce harmful carbon-dioxide emissions. This would increase the resilience of the U.S. energy system against natural disasters and help mitigate global warming, a major factor responsible for the increased frequency and intensity of such disasters [1]. As a preliminary step toward designing a VAWT for a specific urban environment, a VAWT was investigated and modeled during this project.

Engineers are increasingly considering AI tools to automate and accelerate repetitive tasks that characterize many engineering jobs but do not necessarily require engineering expertise. AI tools have developed rapidly and can now assist with documentation, formatting, CAD modeling, and simulation. AI can also support research and information organization, which are critical during the early stages of engineering design work. An example is Andrej Karpathy’s LLM wiki, a pattern for a structured knowledge base in which an LLM organizes and maintains cross-linked Markdown documents that catalog knowledge from a collection of raw sources [2].

### 1.2 Scope and reporting boundary

The project was conducted remotely by Anna and Julie over an eight-week period, with support from Professor Mike Kinsinger and liaisons at 99P Labs. Work was divided between research, source organization, design screening, CAD development, and CFD preparation. OpenCode, Obsidian, Slack, GitHub, and VS Code Live Share were used to maintain a shared project record and support asynchronous collaboration.

This report presents the research system, preliminary airport context, concept-selection process, CAD development, and airfoil-validation work completed to date. A final turbine design, validated full-turbine CFD result, airport installation approval, structural design, manufacturing plan, and measured performance are not claimed.

## 2. LLM Wiki and VAWT Research

### 2.1 Establishing the technical baseline

During the first week, fluid-mechanics concepts, a previous capstone report, VAWT literature, and report appendices were reviewed while meetings were held with the HRI 99P team. Through this initial study, the required technical vocabulary was established, and the need to learn both VAWT design and the new software workflow before the design phase was identified.

A shared digital workspace was then established with OpenCode, Visual Studio Code, Obsidian, Slack, GitHub, and VS Code Live Share. An introductory LLM-wiki workshop, repository creation, shared GitHub access, and asynchronous Git practice were completed. These setup tasks provided the baseline knowledge needed to operate and maintain the wiki. The resulting repository was intended to serve as the shared technical record for research, decisions, CAD, CFD, AI-use lessons, and VAWT information.

### 2.2 Building an LLM wiki

The repository was organized so that raw source material was separated from an agent-editable wiki containing generated summaries and concept notes. Broad behavior and quality rules were specified in an agent contract, `AGENTS.md`, while detailed conversion, ingestion, extraction, organization, and maintenance procedures were placed in a separate `schema/` folder. This separation was introduced after early failures showed that general instructions or an excessively long agent contract did not reliably produce all required behaviors. When general rules and repeatable tasks were separated, the agent could be directed to task-specific instructions, and output consistency was improved.

Research PDFs were converted to Markdown through the source-ingestion workflow while headings, figures, captions, equations, source identifiers, and traceability were preserved where possible. Python and PyMuPDF were added to improve image extraction, which was not initially performed reliably. Incorrect conversions were subsequently repaired; original PDFs that had been removed before the current procedure were restored; unwanted source summarization was corrected; image placement and links were repaired; and missing metadata was added.

The wiki was organized around concepts, methods, designs, and parameters rather than as one undifferentiated note per paper. For each ingested paper, raw text and images were retained in a Markdown file, a short summary note was created, and newly identified concepts were added to or used to create focused notes. A structured wiki was thereby produced that could be used as a reference while turbine concepts and design parameters were studied.

Design choices, including airfoil shape, rated speed, and blade count, could then be compared against startup behavior, cut-in speed, and power coefficient. Obsidian tags, properties, backlinks, bases, graphs, and Dataview were explored so that relationships among sources and decisions could be made visible.

### 2.3 Reliability findings from the research stage

The wiki became useful for source-grounded retrieval and quiz-based learning, but not every ingestion task was performed reliably without supervision. Timeouts, missing figures and equations, poor formatting, malformed links, altered source content, incomplete metadata, and difficulty extracting graph-derived values such as `Cp` were recorded. In response, procedures were tightened and outputs were manually checked rather than treated as automatically correct. Variable outputs were also produced by different models. After specific, repeatable task instructions were created for processes such as source ingestion and figure extraction, the frequency of these failures was reduced.

This stage established a central project result: the usefulness of AI-assisted retrieval was determined by information architecture and verification. A polished answer, a complete-looking wiki page, or a calculated ranking was not independently valid unless the underlying source evidence and assumptions had been checked.

## 3. Site Definition and Design Requirements

### 3.1 Boston Logan context

The open-ended VAWT question was narrowed to Boston Logan International Airport, with Governor’s Island considered as a preliminary location. Logan was selected because high-resolution wind data were accessible and the location represented a plausible high-energy-demand context with stated decarbonization interest. An average wind speed of approximately `5 m/s` was recorded in the project report, while the concept-ranking record used an average wind speed of `4.8 m/s` and average gusts of `6.3 m/s`. These values require reconciliation against the underlying wind-data analysis before final submission.

Two years of site wind data were added to the wiki and used to generate a wind-speed histogram and establish early design priorities. Airport airspace regulations were also examined, and Governor’s Island was identified as a preliminary candidate area. The `>= 700 ft` runway-edge criterion was recorded as a planning note in the design-goal record; it was not evidence that airport installation approval had been granted.

### 3.2 Design criteria

The design goal was defined to prioritize competitive efficiency, low-speed operation appropriate to the site, manufacturability, minimal maintenance, economic feasibility, airport-regulation compliance, CAD feasibility, and compatibility with good CFD practices within the project timeline.

For concept screening, these priorities were translated into seven criteria: startup ability, with a target of `<= 3 m/s`; efficiency and economics; rated-speed fit around `10-15 m/s`; cut-out-speed fit around `>= 20 m/s`; room for future iteration; CAD and manufacturing feasibility; and team interest. Startup and efficiency were each assigned 35% of the original weighted score. CAD and manufacturability were assigned 15%, rated-speed fit was assigned 10%, and room for growth and cut-out fit were each assigned 2.5%.

> Uncertainty: The target power, final installation point, site-specific height limit, generator/load curve, and approved airport-clearance constraints remain open. The current criteria are suitable for early screening, not a final requirements specification.

## 4. Concept Selection

### 4.1 From 63 designs to a focused candidate set

When formal screening began, 63 VAWT designs were contained in the research wiki. A first pass was conducted independently by Anna and Julie with LLM assistance, and approximately 8-10 promising concepts were identified by each reviewer. After the lists were compared, six designs were selected for detailed scoring. Straight-bladed H-rotor Darrieus, helical Darrieus, reduced-interference hybrid, Savonius-derived, involute, shifted-troposkien, and other source-specific concepts were represented in the candidate set.

Independent human scoring was deliberately combined with AI-assisted ranking. The LLM was used to retrieve structured evidence, compile comparison tables, and calculate weighted scores. Human scores were retained for qualitative criteria such as team interest and perceived CAD difficulty. Criterion weights were then varied for beginner, expert, and performance-focused personas to determine whether a narrow result depended on one assumption set.

### 4.2 Ranking result

Under the initial weighting, the self-starting straight-bladed H-rotor Darrieus path was ranked first with a weighted score of `4.40/5`, and VJ20 was ranked second at `4.25/5`. In the narrower H-type comparison, VA9 was ranked first at `4.30/5` and VJ20 second at `4.25/5`. Because the difference was small, both concepts were advanced rather than treating a single calculated score as a final selection.

A meaningful tradeoff was represented by the two selected concepts. VA9 was supported by reported low-speed-startup evidence, including a reported `1.25 m/s` self-start and `Cp = 0.416`. VJ20 was supported by a higher reported `Cp` near `0.486`, a reported full-scale cut-in of `2.81 m/s`, and a dual-rotor architecture that introduced additional complexity.

The sensitivity analysis reinforced the decision to retain both designs. VA9 remained higher under startup-, simplicity-, and beginner-focused weights, whereas VJ20 was ranked higher in the expert BOS-performance scenario, with a score of `4.28/5` compared with VA9’s `4.13/5`.

### 4.3 A quantitative-AI failure that changed the process

During manual review, it was found that VJ20’s cut-in speed had been misreported by the LLM during the ranking process. Julie’s log records that a `2.9 m/s` value from another design had been cited in the original output, while a later secondary-source check reported a VJ20 cut-in value of `1.5 m/s`; the current worksheet lists a VJ20 full-scale cut-in of `2.81 m/s`. The conflicting values demonstrate that the metric definition, scale, and source context must be resolved from the primary VJ20 paper before the value is used in a final ranking.

The important outcome was not merely that one AI-derived number was corrected. The operating rule was changed so that quantitative values, especially values missing from text or presented in figures, must be verified against the primary source before they influence a consequential design decision.

## 5. CAD Development

### 5.1 Objective and tools

CAD was used as a feasibility test and preparation stage for later CFD, not as proof of a final turbine design. Zoo Design Studio and its ZooKeeper agent, including KCL, were explored, and Fusion’s Autodesk Assistant was later compared. The tools were evaluated for their ability to convert research-supported specifications into editable geometry and to support changes without loss of traceability.

CAD prompts were recorded, and source-backed dimensions were distinguished from inferred support hardware. This record was required because convincing geometry can be created even when every structural dimension, airfoil coordinate, or connection detail has not been specified by the source.

### 5.2 VA9 reconstruction

VA9 could not be fully reconstructed because complete CAD-ready geometry was not provided in the paper. The documented source-backed dimensions were a `36.0 cm` blade-body height, `48.0 cm` rotor height, `17.3 cm` rotor radius, and `5.3 cm` chord. A main blade body with two inward-positioned blade ends was described, but an EN0005 coordinate set, support dimensions, and a definitive blade-end angle were not provided.

A parameterized VA9 assembly was created, and iterations were concentrated on the blade ends. The final logged approximation retained a `46 deg` inward rake and smoother lofted transitions after rotated extrusion, trim, loft behavior, intermediate profiles, cup depth, outer-lip width, and a denser profile trace had been tested. These were modeling choices for an approximation, not source-validated aerodynamic dimensions.

The body and blade ends could not be robustly boolean-unioned after the profile became denser, so touching but separate bodies were retained. Consequently, a visual render must not be interpreted as a watertight solid suitable for manufacture or CFD.

### 5.3 VJ20 reconstruction

More complete published rotor specifications were available for VJ20. The model was defined as two concentric straight-bladed H-rotors on a shared shaft: three outer NACA0018 blades, three inner DU 06-W-200 asymmetric-airfoil blades, `120 deg` spacing within each three-blade rotor, and a `60 deg` phase offset between the rotors. Unreported features, including a Savonius rotor, helicity, taper, variable pitch, shrouds, and guide vanes, were prohibited in prompts. Support hardware was deliberately labeled as inferred and editable.

Complex initial assemblies were generated rapidly by ZooKeeper, but tool-level success did not guarantee usable geometry. Disconnected blades, floating blocks around inner blades, a missing inner top strut after a repair, incorrect inner brackets, and instability during rotor-azimuth changes were observed. KCL was read and the agent was asked to identify modified code lines, which improved inspection and repair capability but did not eliminate the need for independent CAD expertise.

Full-scale and `1/11.01` scaled VJ20 models were generated more quickly by Fusion than by ZooKeeper in one trial. Later inspection showed that the Fusion inner blades did not use the required DU 06-W-200 asymmetric airfoil. The model is therefore useful as a visual and CFD-planning starting point, not as a source-faithful VJ20 reproduction.

### 5.4 CAD result

The CAD work showed that first-pass parametric geometry can be accelerated by AI, but visual inspection, source traceability, and manual model understanding are made more important rather than less important. VA9 remains useful as a parameterized approximation with unresolved source geometry and multi-body issues. VJ20 remains the more tractable baseline because more source geometry is available, but its inner-airfoil fidelity, connections, watertightness, and CFD-specific simplification require verification.

## 6. CFD Setup and Airfoil Validation

### 6.1 Purpose of the validation study

Before CFD was used to compare VAWT designs, an attempt was made to establish a defensible airfoil workflow. The active study used a NACA0018 airfoil at `Re = 50,000`, `5 deg` angle of attack, `1.0 m` chord, `0.7645 m/s` inlet velocity, and air density `1.196 kg/m3`. The early comparison target was an AirfoilTools curve of approximately `Cl = 0.75` at the stated condition.

The later common setup was defined as an incompressible, steady-state `k-omega SST` case with a velocity inlet, pressure outlet, slip outer boundaries, no-slip airfoil walls, and lift and drag coefficients defined along `+y` and `+x`, respectively. The study was repeatedly revised as finite-span effects, pseudo-two-dimensional modeling, boundary layers, `y+`, mesh quality, non-orthogonality, and trailing-edge geometry were investigated.

### 6.2 Key experimental sequence

Several external-flow domains and mesh choices were used in the first batch. NACA0018 predictions ranged from `Cl = 0.1306` to `0.261` and `Cd = 0.0397` to `0.061`, substantially below the lift comparison value. No usable results were produced by one early pseudo-two-dimensional run because result controls had not been configured. These outcomes were exploratory and did not provide a validation basis.

A comparability problem was then identified: an initial finite-span, three-dimensional airfoil case could not be directly compared with two-dimensional sectional data. When the spanwise flow volume was reduced to `0.5 m` and the reference area was corrected from `1 m2` to `0.5 m2`, the recorded NACA0018 result changed from `Cl = 0.291`, `Cd = 0.026` with the inconsistent area to `Cl = 0.583`, `Cd = 0.052` with the corrected area. This change demonstrated that coefficient normalization and dimensionality are physical-setup decisions, not postprocessing details.

Mesh fineness, first-layer thickness, wall treatment, turbulence intensity, non-orthogonal correctors, and trailing-edge geometry were then varied. When fineness was increased to 8, `Cl = 0.515` and `Cd = 0.041` were produced. When the trailing edge was rounded, a `0.00001 m` first layer was used, and two non-orthogonal correctors were applied, a lower maximum `y+` of `4.913` was produced with `Cl = 0.570` and `Cd = 0.028`; at fineness 7, `Cl = 0.572` and `Cd = 0.030` were produced.

### 6.3 Control cases and interpretation

Using the same key rounded-tail setup, the NACA0012 control produced `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`. Direct STEP inspection confirmed an approximately `1 m` chord, nominal 12% and 18% thicknesses for the NACA0012 and NACA0018 geometries, and a `0.5 m2` reference area for the retained pseudo-two-dimensional wetted section.

The NACA0012 control supports the conclusion that no currently observed shared domain, reference-area, orientation, scale, or rounded-tail-CAD issue explains the NACA0018 discrepancy. It does not prove that the NACA0018 AirfoilTools comparison is incorrect, validate the rounded NACA0018 as an ideal sharp profile, establish mesh independence, or validate a VAWT CFD workflow.

The literature record also identifies a low-turbulence NACA0018 experiment with different low-Reynolds-number behavior, including `Clmax = 0.435` at `Re = 50,000` and `3 deg`. AirfoilTools is therefore not the only relevant reference context, and the remaining discrepancy cannot be confidently assigned to one solver setting.

### 6.4 Current CFD status

The best documented NACA0018 result is approximately `Cl = 0.57` and `Cd = 0.028-0.030` for a steady, `k-omega SST`, rounded-NACA0018 pseudo-two-dimensional SimScale case. It must be reported as a model-specific prediction, not as an experimentally validated coefficient.

Later mesh-refinement work improved mesh appearance and varied boundary-layer count, overall thickness, growth rate, surface sizing, volume refinements, and local-refinement placement. Results remained inconsistent, and residual, non-orthogonality, and reference-benchmark concerns remain in the record. The effort was therefore redirected from forcing agreement with a single target toward documenting the case and seeking a condition-matched benchmark and expert review.

## 7. Assessment of AI in the Workflow

### 7.1 Benefits observed

The highest-value AI uses were found in retrieval across a curated source set, organization of research into comparable notes, generation of candidate work plans, calculation of weighted decision scores, initial CAD generation, and guided learning through explanations and quizzes. These applications accelerated the transition from a broad literature collection to a structured design conversation.

Repeated ranking and sensitivity scenarios were made practical by AI, while human-defined criteria and independent scores preserved a means of inspecting the result. CAD tools likewise enabled complex initial assemblies to be generated and compared before equivalent conventional models could have been created at the same level of detail. Time was also saved when source records could be searched, summarized, and cross-linked through the wiki rather than manually located for every question.

### 7.2 Costs, limits, and failures

The apparent time savings carried direct verification costs. Generated source conversions had to be checked and repaired. Quantitative values required primary-source verification, particularly when values were presented in graphs or when several experimental contexts appeared in one paper. CAD assemblies required manual inspection for airfoil identity, disconnected bodies, support geometry, and watertightness. The VJ20 cut-in-speed misreport, malformed conversions, missing figures, incorrect CAD airfoil, disconnected geometry, and repetitive CFD advice show that AI output must be treated as a proposal for review rather than as a completed engineering task.

Additional costs were incurred in learning and workflow management. Time was required to create procedures, revise prompts, compare models, inspect generated code, record iterations, and recover from tool failures. Model variability made successful results difficult to reproduce consistently. As CFD cases became more specific, generalized AI troubleshooting became repetitive and less useful, so expert review and direct investigation were still required. No project-specific monetary cost comparison was conducted; the costs assessed here are time, verification effort, reproducibility risk, and the risk of incorrect technical decisions.

A learning tradeoff was also identified. Fast synthesis can reduce time spent directly engaging with papers and working through technical concepts, thereby weakening deep understanding. This risk was mitigated by reviewing source documents, using the wiki for quizzes and explanations, retaining written records of assumptions and failures, and requiring human judgment for criteria, evidence quality, geometry inspection, and final decisions.

### 7.3 Interim workflow principle

The evidence supports a human-led workflow. AI should be used to broaden search, organize information, expose alternatives, perform transparent calculations, and create first-pass artifacts. Objectives should be defined by humans; source quality, quantitative values, geometry, acceptable tradeoffs, and validation sufficiency should also be judged by humans.

## 8. Conclusions and Remaining Work

By the reporting cutoff, a substantial research and screening phase had been completed, a technical knowledge system had been built, VA9 and VJ20 had been selected as leading concepts, exploratory CAD models had been generated, and a detailed record of an incomplete airfoil CFD-validation effort had been created. A validated final VAWT had not been produced, but a traceable foundation had been established for the remaining design and validation work.

The remaining work should prioritize the smallest set of actions that produces defensible evidence: baseline CAD geometry and CFD suitability should be verified; the CFD benchmark and mesh-quality acceptance criteria should be resolved; only staged simulations with confirmed controls and outputs should be run; and final AI-workflow lessons from both successes and failures should be documented.

> Uncertain: The final VAWT geometry, airport-installation feasibility, full-turbine CFD results, aerodynamic performance, and manufacturing feasibility are not established by the current record.
>
> Check next: Confirm source-level VJ20 operating values; select a matched NACA0018 benchmark; verify CAD watertightness, airfoil identity, and face groups; and define CFD mesh, convergence, timestep, and periodicity acceptance criteria before interpreting a turbine result.

---

## Appendix A. Project Timeline

| Period | Major completed work |
| --- | --- |
| Week 1, 22-26 June | Fluid mechanics, prior reports, VAWT research, and project references were reviewed; the shared repository and LLM-wiki workflow were established. |
| Week 2, 29 June-3 July | Source conversions were repaired; Python/PyMuPDF image extraction was added; `schema/` procedures were created; metadata, figures, equations, links, and wiki organization were improved. |
| Week 3, 6-10 July | Boston wind data and Logan siting were evaluated; a design goal was created; concepts were screened and ranked; VA9 and VJ20 were selected; AI-CAD work was begun. |
| Week 4, 13-17 July | SimScale and CFD fundamentals were studied; NACA0018 validation was begun; pseudo-two-dimensional setup, reference area, mesh refinement, `y+`, and result controls were explored. |
| Week 5, 20-24 July | Airfoil validation and mesh troubleshooting were continued; full-scale and scaled VJ20 CAD was created; VJ20 CFD setup was begun; the VJ20 cut-in reporting issue was identified. |
| Week 6 onward | Mesh refinement, geometry inspection, documentation, and full-turbine CFD preparation were continued. |

## Appendix B. Concept-Selection Evidence Snapshot

| Item | Recorded value or outcome | Interpretation limit |
| --- | --- | --- |
| Design corpus | `63` VAWT designs in the wiki | Count supports screening scope, not equal evidence quality for every design. |
| Detailed concepts | `6` designs after the initial human/LLM pass | The initial shortlist contained human judgment and may not be exhaustive. |
| Initial ranking weights | Startup `35%`; efficiency `35%`; CAD/manufacturability `15%`; rated-speed fit `10%`; growth `2.5%`; cut-out fit `2.5%` | Project priorities, not universal VAWT optimization weights. |
| VA9 result | `4.40/5`; reported `1.25 m/s` self-start; reported `Cp = 0.416` | Source-specific evidence, not a Logan performance prediction. |
| VJ20 result | `4.25/5`; reported `Cp = 0.486`; reported `2.81 m/s` full-scale cut-in | Startup records conflict across scale and test contexts. |
| Sensitivity result | VA9 was stronger under practicality/startup weights; VJ20 was stronger under expert-performance weighting (`4.28/5` vs `4.13/5`) | Supports advancing both concepts, not declaring a universal winner. |

## Appendix C. CAD Geometry Ledger

| Concept | Source-backed geometry carried into CAD | Inferred or unresolved geometry | Current limitation |
| --- | --- | --- | --- |
| VA9 EN0005 self-start Darrieus | `36.0 cm` blade-body height; `48.0 cm` rotor height; `17.3 cm` rotor radius; `5.3 cm` chord; main body plus inward blade ends | EN0005 coordinates, support dimensions, definitive blade-end angle, and structural design | Blade body and ends remain separate touching bodies; model is an approximation. |
| VJ20 dual H-rotor hybrid | Three outer NACA0018 blades; three inner DU 06-W-200 blades; `120 deg` spacing; `60 deg` phase offset | Hubs, struts, bearings, generator mount, and other mechanical details | Generated models require verification of airfoil identity, connected bodies, and CFD-specific simplification. |

## Appendix D. Airfoil CFD Validation Record

### D.1 Case definition

| Parameter | Value |
| --- | --- |
| Airfoil | NACA0018 |
| Angle of attack | `5 deg` |
| Reynolds number | `50,000` |
| Chord | `1.0 m` |
| Inlet velocity | `0.7645 m/s` |
| Air density | `1.196 kg/m3` |
| Primary model | Incompressible, steady-state `k-omega SST` |
| Pseudo-2D reference area | `0.5 m2` for `1.0 m` chord and `0.5 m` span |

### D.2 Selected results

| Case | Key change | `Cl` | `Cd` | Note |
| --- | --- | ---: | ---: | --- |
| Batch 1 Runs 1-5 | Early domains and meshes | `0.1306-0.261` | `0.0397-0.061` | Exploratory cases; inadequate validation basis. |
| Batch 2 Run 5 | Pseudo-2D span and corrected `0.5 m2` area | `0.583` | `0.052` | Area correction materially changed the coefficient. |
| Run 8 | Mesh fineness `8` | `0.515` | `0.041` | Improved drag but lower lift. |
| Run 13 | Rounded tail, near-wall changes, two non-orthogonal correctors | `0.570` | `0.028` | Maximum `y+ = 4.913`; best documented low-drag case. |
| Run 14 | Run 13 with fineness `7` | `0.572` | `0.030` | Result effectively unchanged. |
| Run 15 control | NACA0012 with Run 13 settings | `0.614` | `0.028` | Tests shared setup elements; does not validate NACA0018. |

### D.3 Limitations retained for final reporting

- No complete mesh-independence, domain-independence, convergence, transition-model, or cycle-repeatability study has been documented.
- The rounded NACA0018 geometry is not an ideal sharp trailing-edge NACA0018.
- AirfoilTools and the low-Reynolds-number NACA0018 experiment represent different reference contexts; neither alone resolves validation.
- The NACA0010 supplementary drag value should be checked against the saved SimScale output before it is included in a final report.

## Appendix E. Recommended Figures

1. A project workflow diagram showing research sources, conversion procedures, wiki, site criteria, ranking, CAD, CFD, and human verification.
2. A Boston Logan wind-speed histogram with station, time period, units, and processing method stated in the caption.
3. The concept-ranking table with weights and uncertainty labels for inferred or missing data.
4. A VA9 render annotated to distinguish source-backed and inferred geometry.
5. A VJ20 render showing blade count, rotor phase, and airfoil-verification status.
6. A CFD mesh and coefficient-history figure that identifies the exact run, geometry, mesh settings, reference area, and convergence status.

## Appendix F. Project Records Used for This Draft

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

# Appendix I. Airfoil CFD Validation Process and Current Status

## I.1 Goal and general approach

Before applying CFD to a full VAWT, the team attempted to establish a defensible airfoil-level workflow using a NACA0018 case. The purpose was to determine whether the selected SimScale setup could reproduce a suitable reference lift and drag condition before interpreting full-turbine torque or power-coefficient results. This was a validation attempt, not a completed validation of the airfoil, the final turbine, or SimScale as a general CFD workflow.

The work began by adapting the prior HRI airfoil-validation procedure, then progressed through exploratory domain and mesh tests, a pseudo-two-dimensional comparison setup, mesh-quality and near-wall refinements, and control cases using NACA0012, NACA0010, and NACA0015. The team used the logs to track each case, inspected mesh images and quality metrics, checked STEP geometry and coefficient normalization, and sought CFD-expert feedback when AI-assisted troubleshooting did not resolve the discrepancy.

## I.2 Best-documented later simulation setup

The later rounded-trailing-edge NACA0018 case was the most consistently documented configuration. It should be treated as the definition of the reported model output, not as a universally correct validation recipe.

| Setup item | Recorded configuration |
| --- | --- |
| Airfoil | NACA0018 with a rounded trailing edge in the later cases |
| Angle of attack | `5 deg` |
| Nominal Reynolds number | `50,000` |
| Chord | `1.0 m` |
| Fluid | Air; density `1.196 kg/m3`; kinematic viscosity `1.5293e-5 m2/s` |
| Inlet velocity | `0.7645 m/s` |
| Solver | Incompressible, steady-state `k-omega SST` |
| Computational domain | External-flow volume: `x = -10` to `15 m`; `y = -8` to `8 m`; `z = -0.25` to `0.25 m` |
| Dimensionality treatment | A `0.5 m` spanwise external-flow volume was used as a pseudo-2D approximation so the case could be compared more meaningfully with sectional airfoil data. |
| Inlet | Velocity inlet, `Ux = 0.7645 m/s`; later cases specified turbulence intensity `0.001`. |
| Outlet | Pressure outlet, gauge pressure `0 Pa`. |
| Outer boundaries | Slip walls on the outer boundaries. |
| Airfoil boundary | No-slip airfoil wall. The run log labels the later rounded-tail case as a wall-function case, while a later meeting brief reports full-resolution treatment; the saved SimScale case must be checked before either wall-treatment label is used as final evidence. |
| Force-coefficient controls | Lift along `+y`; drag along `+x`; reference velocity `0.7645 m/s`; reference length `1 m`; reference area `0.5 m2`. |
| Numerics | Two non-orthogonal correctors in the best-documented rounded-tail case. |
| Simulation control | End time `1000 s`; time step `1 s`; write interval `1000` time steps. |
| Near-wall mesh changes in Run 13 | First-layer size `0.00001 m`; small-feature suppression `0.000001 m`; rounded trailing edge. |

The `0.5 m2` reference area is important. The STEP review found that the `1 m`-chord airfoil body was physically extruded to `1 m` span, but the pseudo-2D external-flow volume retained only `0.5 m` of wetted span after subtraction. Using `A = chord x span = 1.0 m x 0.5 m = 0.5 m2` therefore corrected an earlier coefficient-normalization inconsistency.

## I.3 Troubleshooting record: issue, response, and impact

| Issue encountered | What was changed or checked | What was learned | Impact on mesh or simulation result |
| --- | --- | --- | --- |
| Early NACA0018 runs predicted very low lift and high drag. | Tested default meshing, boundary-layer inflation, Hex Automatic meshing, and different external-flow volumes. | The first cases were exploratory and did not provide a sufficient validation basis. | Batch 1 results ranged from `Cl = 0.1306-0.261` and `Cd = 0.0397-0.061`; no early configuration matched the intended lift comparison. |
| The first attempted pseudo-2D run produced no usable results. | Rebuilt the case with explicit force and moment result controls. | Result controls must be configured before a run; solver completion alone does not produce usable validation evidence. | The failed run was not used for coefficient comparison. |
| A finite-span model was being compared with a sectional airfoil reference. | Reduced the spanwise domain from a large finite span to `z = -0.25` to `0.25 m`. | A pseudo-2D treatment was more appropriate for comparison with 2D reference data; finite-span effects were distorting the comparison. | Before correcting area, the reduced-span case gave `Cl = 0.291`, `Cd = 0.026`; after area correction, the same general setup gave `Cl = 0.583`, `Cd = 0.052`. |
| Coefficients were normalized with the former `1 m2` area after the span was shortened. | Changed the force-coefficient reference area to `0.5 m2` and later checked the retained wetted span in the STEP/domain geometry. | Coefficient reference area is part of the physical setup, not a cosmetic postprocessing choice. | Reported lift increased from `Cl = 0.291` to `Cl = 0.583`; the corrected area was retained. |
| Enlarging the outer domain did not improve the low-lift result. | Expanded the finite-span domain from `x = -3` to `8 m`, `y = -4` to `4 m`, `z = -4` to `4 m` to `x = -10` to `15 m`, `y = -8` to `8 m`, `z = -8` to `8 m`. | Domain enlargement alone was not the main explanation for the discrepancy. | The log records essentially no change before the pseudo-2D change. |
| Maximum solved `y+` was too high for the intended near-wall target. | Added `y+` monitoring; varied first-layer thickness, wall treatment, and boundary-layer settings. | Tracking `y+` exposed that early near-wall changes did not automatically improve the solution; an inflation refinement can also override automatic boundary-layer settings. | The duplicate corrected pseudo-2D case recorded maximum `y+ = 18.61`; later turbulence/mesh cases recorded maximum `y+` near `20.11`. |
| Global mesh fineness changed drag more than lift. | Increased fineness to `8`. | More global refinement was not a substitute for a controlled near-wall and trailing-edge mesh strategy. | `Cl` decreased to `0.515`, while `Cd` improved to `0.041`. |
| Changing inlet turbulence and wall treatment did not resolve the lift gap. | Changed turbulence from automatic to intensity `0.001`; tried full-resolution treatment in one run. | These changes were not isolated enough to determine a universal effect, but they did not materially remove the NACA0018 lift discrepancy. | A stabilized low-intensity case recorded `Cl = 0.570`, `Cd = 0.051`, and maximum `y+ = 20.11`; subsequent full-resolution testing was recorded as essentially unchanged. |
| Sharp trailing-edge meshing produced high non-orthogonality near the trailing edge. | Reduced first-layer size, adjusted small-feature suppression, and rounded the trailing edge; increased non-orthogonal correctors from one to two. | Geometry repair can be necessary when the mesher cannot create a usable prism-layer transition at a sharp feature. The rounded geometry is no longer an ideal sharp NACA0018. | Run 13 reached maximum `y+ = 4.913`, with `Cl = 0.570` and `Cd = 0.028`; drag and near-wall quality improved, but lift did not. |
| Mesh refinements looked better but residuals and coefficients remained unsatisfactory. | Julie created multiple boundary-layer, surface, volume, and wake refinement variants; Anna and Julie inspected non-orthogonality, aspect ratio, and local cell transitions with expert feedback. | A visually improved mesh is necessary but does not itself validate force coefficients. Refinement boxes can conflict, create abrupt size changes, or increase run cost. | Later meshes improved local quality in some cases, but the logs record residuals around `1e-5` and no final convergence or mesh-independence demonstration. |
| It was unclear whether a shared setup or the NACA0018 geometry caused the discrepancy. | Ran a NACA0012 control under the rounded-tail setup and inspected STEP scale, thickness, orientation, span, and topology. | The shared domain, reference area, scale, and orientation workflow could produce a close NACA0012 comparison, but that did not validate NACA0018. | NACA0012 Run 15 gave `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`; NACA0018 remained near `Cl = 0.57`. |
| The reference target itself was not condition-matched. | Compared the AirfoilTools target with the low-Reynolds-number NACA0018 source record and discussed shifting to wind-tunnel data. | Different reference sources can represent different Reynolds numbers, transition states, geometry, or turbulence conditions; matching one curve is not a sufficient definition of validation. | The work stopped short of forcing the NACA0018 result to the AirfoilTools value and instead recorded the result as model-specific. |

## I.4 Validation targets compared with the current evidence

| Quantity or acceptance question | Target or expectation during the study | Best documented end state | Interpretation |
| --- | --- | --- | --- |
| NACA0018 lift coefficient at `Re = 50,000`, `5 deg` | AirfoilTools-based comparison of approximately `Cl = 0.75`. | Best rounded-tail pseudo-2D cases recorded `Cl = 0.570-0.572`. | The original lift comparison was not met. A separate low-Re source has a different reference context, so the gap cannot be attributed confidently to one simulation setting. |
| NACA0018 drag coefficient | Match the selected reference curve; the project record did not establish one final numerical `Cd` acceptance value. | Best rounded-tail cases recorded `Cd = 0.028-0.030`. | Drag improved substantially from the early `0.04-0.06` range, but no condition-matched drag-validation criterion was completed. |
| Residual convergence | CFD-expert guidance recorded a target below `1e-10`, ideally around `1e-15`, for `k` and `omega`. | Julie recorded residuals around `1e-5` in the later mesh work and questioned whether the expert target was achievable; no final residual-history acceptance result was documented. | The record does not demonstrate convergence to the stated expert target. |
| Boundary-layer appearance | Smooth, uncrushed prism layers with a gradual transition from near-wall cells to the free stream; no abrupt jump in cell size. | Many boundary-layer count, thickness, growth-rate, and refinement variants were tested. The rounded-tail Run 13 mesh reduced `y+`, while later variants still showed crushed layers or abrupt size transitions. | Boundary-layer quality improved but was not closed by a documented mesh-independence or final visual acceptance criterion. |
| Solved `y+` | CFD-expert guidance was `y+ < 1` for the intended wall-resolution approach. | Run 13 recorded maximum `y+ = 4.913`; Run 14 recorded `4.924`; the NACA0012 control recorded `5.33`. | The recorded cases improved greatly from roughly `18-20`, but did not meet the stated `< 1` target. The appropriate wall-treatment and `y+` requirement remain unresolved because the log contains conflicting wall-function and full-resolution labels. |
| Mesh quality | Avoid high non-orthogonality, high aspect ratio, crushed prism layers, and isolated poor cells near sharp features or transitions. | Rounding the trailing edge reduced a key trailing-edge issue; later mesh variants reported non-orthogonality from approximately `72` to `83` in selected cases, while supplemental NACA0010/0015 controls reached roughly `87-89`. | Mesh quality was actively improved and inspected, but no final mesh-quality threshold or mesh-independence result was satisfied and documented. |
| Coefficient stability | Lift and drag histories should flatten before coefficients are interpreted. | Some runs were extended to reduce residuals; one low-turbulence case showed oscillating `Cl`. | No complete force-history or convergence acceptance record exists for the NACA0018 result. |
| Geometry and normalization | Correct chord, thickness, orientation, wetted span, and reference area. | STEP review confirmed nominal `1 m` chord, nominal `18%` thickness, `0.5 m` retained span, and `A = 0.5 m2`; orientation was corrected in SimScale. | These checks ruled out several shared setup errors but do not validate the rounded NACA0018 aerodynamic result. |
| Control-case behavior | A common setup should produce a credible result for a suitable control profile. | NACA0012 Run 15 recorded `Cl = 0.614`, `Cd = 0.028`, and maximum `y+ = 5.33`, described in the log as close to its target. | This supports parts of the shared workflow, but one successful control cannot validate a different airfoil with a different trailing-edge response or transition behavior. |

## I.5 Current conclusion and required next checks

The best-supported current result is not a validated NACA0018 coefficient. It is a prediction from a steady, `k-omega SST`, rounded-trailing-edge, pseudo-2D SimScale case at the recorded condition: approximately `Cl = 0.57`, `Cd = 0.028-0.030`, and maximum `y+` near `4.9`. The strongest improvements were the pseudo-2D/reference-area correction and the trailing-edge mesh repair; these improved coefficient normalization, drag, and near-wall metrics without resolving the lift gap.

Before this workflow is used to compare VAWT aerodynamic performance, the project needs a condition-matched NACA0018 benchmark with documented geometry, Reynolds number, angle of attack, transition and turbulence conditions, dimensionality, and measured coefficients. It also needs a controlled one-variable-at-a-time mesh and domain sensitivity sequence, a verified wall-treatment and `y+` target, residual and force-history acceptance criteria, and confirmation of the final saved SimScale settings. Until then, the airfoil coefficients should be presented as model outputs rather than validated physical values.

**Appendix I source records:** `active/_anna daily log.md`; `active/_Julie_daily_log.md`; `active/documentation/CFD log/Airfoil Validation Studies.md`; `active/documentation/CFD log/Airfoil Validation Study Summary and Report Outline.md`; `active/documentation/CFD log/CFD Expert Meeting Brief.md`; `sources/cj9.md`.
