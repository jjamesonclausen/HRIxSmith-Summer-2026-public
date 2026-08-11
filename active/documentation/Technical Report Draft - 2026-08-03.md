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
