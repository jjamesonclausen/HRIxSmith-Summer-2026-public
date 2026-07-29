---
tags:
  - report
---

`Prompt:` I need to start preparing to write a narrative-style report about this project. Recall that the two goals of the project are to design a vawt and to learn how to implement AI tools into an engineering workflow. Read through \_anna daily log.md and note the bullet points indicating what tasks have been completed each day, as well as the italic text that documents my experience using AI. Write a log summary and report outline that captures the progress that was made in the first four weeks and the lessons learned about AI utility.

**Source:** [[_anna daily log]]

## Scope

This note synthesizes the completed-work bullets and italicized AI-use reflections for Weeks 1-4, from June 22 through July 17 from Anna's daily log. It supports a narrative report about the two project goals: designing a vertical-axis wind turbine (VAWT) and learning to integrate AI tools into an engineering workflow.

# Four-Week Log Summary

### Week 1: Establish the research and AI workflow

- Began the project by reviewing prior VAWT project material, researching VAWTs, refreshing fluid-mechanics knowledge, and meeting the Honda Research Institute / 99P team.
- Set up OpenCode, Obsidian, Slack, and the project repository; explored the LLM-wiki workshop and its source-grounded, citation, uncertainty-labeling, anti-sycophancy, and evaluation-loop rules.
- Added sources, tested ingestion and question answering, strengthened agent rules and source-intake procedures, created a shared GitHub repository, and collaborated through VS Code Live Share.
- Developed PDF-to-Markdown and figure-extraction procedures, created an evaluation-question set, and iteratively tested the wiki.

**AI utility:** The wiki showed early value as a trusted, cited learning and retrieval tool. Quiz-based interaction prompted more active reading, and explicit instructions made the model more candid than a generic chatbot. The cost was substantial upfront work to find sources, configure procedures, and evaluate outputs.

### Week 2: Make the wiki reliable and useful for design comparison

- Added and repaired sources; investigated PDF image embedding and used Python/PyMuPDF to improve figure extraction.
- Separated general rules in `AGENTS.md` from task-specific documents in `schema/`; refined conversion, source-ingestion, maintenance, metadata, equation, figure, and link-verification procedures.
- Learned Obsidian organization, metadata, tags, properties, Dataview, bases, and graph tools; created design and parameter page structures so VAWT concepts could be compared.
- Repaired converted sources and broken backlinks; created and tested `wiki/designs/` and `wiki/parameters/`, then created design and parameter pages for the available sources.

**AI utility:** AI could convert sources, extract images, and draft useful wiki pages, but performed those tasks inconsistently. Formatting and image failures required extensive human correction, and malformed metadata could undermine later database and search use. This made verification and specific procedural constraints essential rather than optional.

### Week 3: Turn research into a VAWT design decision and initial CAD

- Investigated Boston-area wind data, selected Logan Airport as the preferred location, considered airport constraints and Massport's net-zero motivation, and used the wiki to assess local VAWT suitability.
- Updated design metadata to record numerical performance values in wind-speed buckets aligned with the observed Boston wind range, later adding an 8-12 m/s bin.
- Defined the design goal and timeline, organized CFD and CAD documentation, and used AI-generated work plans as inputs for human comparison and discussion.
- Built a design-concept list and criteria, independently ranked alternatives, compared those rankings with LLM rankings, selected weights, and used the LLM to calculate weighted scores. The team narrowed the leading candidates to the `vj20` hybrid and `va9` EN0005 designs.
- Learned Zoo Design and Zookeeper, generated an initial `vj20` CAD model from wiki-supported prompts, and began manually inspecting and debugging its KCL structure with OpenCode assistance.

**AI utility:** The wiki accelerated cross-source retrieval, ranking, score calculation, work-plan generation, and first-pass CAD generation. However, AI-assisted selection risked replacing the slow reading in which the team would otherwise build design intuition. Rankings required human review because the model could infer missing quantitative data or choose values that contradicted a paper's final conclusion. Shorter CAD prompts produced better initial results, but AI-generated geometry was difficult to modify or repair without understanding the underlying model.

### Week 4: Build CFD capability and test the limits of wiki-guided troubleshooting

- Learned CFD and SimScale fundamentals through a flow-simulation tutorial and the previous project report; attempted a pseudo-2D airfoil validation study.
- Used the wiki to understand the prior validation workflow and troubleshoot mesh and setup choices, including boundary-layer inflation, mesh growth rate, and meshing approach.
- Added SimScale documentation to the wiki, learned the components of CFD simulation, conducted additional NACA0018 validation attempts, and researched CFD background and prior project methods.
- Systematically varied airfoil geometry, computational-domain dimensions, pseudo-2D spanwise extent, first-layer thickness and `y+`, and mesh fineness; identified tip vortices as a reason that the shortened spanwise domain improved lift.
- Added low-Reynolds-number airfoil and CFD sources and had the LLM locate and ingest relevant SimScale-forum threads.

**AI utility:** Adding authoritative SimScale documentation quickly improved general learning, but it did not provide sufficiently specific troubleshooting guidance. Broader generic-AI advice could be more relevant because it drew on the internet, but was less trustworthy. Adding targeted low-Reynolds-number and airfoil sources improved the wiki's advice, although it remained repetitive and poor at tracking the exact changes between simulation runs. AI made an unfamiliar CFD process feel more informed, but did not replace the need for experiment records, source expansion, and validation.

# Narrative Report Outline

### 1. Introduction: A dual engineering experiment

- Introduce the paired objectives: develop a VAWT design for the selected context and test whether a source-grounded LLM wiki plus AI design tools can improve an engineering workflow.
- Frame the report as a narrative of increasing technical specificity and calibrated trust in AI, rather than a claim that automation independently designed the turbine.

### 2. Starting point: Building a trustworthy knowledge system

- Describe the initial VAWT background review, prior-report study, and onboarding with collaborators.
- Explain the initial hesitation about AI: preserving research, writing, and reasoning skills while using AI for debugging or unfamiliar programming.
- Describe the LLM wiki architecture: immutable sources, citation requirements, explicit uncertainty labels, anti-sycophancy rules, procedures, and evaluation questions.
- Report the first lesson: AI retrieval and Socratic quizzing can support learning when grounded in vetted sources, but building a reliable system carries an upfront cost.

### 3. The hard part of AI integration: reliability, not generation

- Narrate the work to ingest PDFs, extract figures, organize metadata, repair formatting, and collaborate through Git and Obsidian.
- Use concrete failures: inconsistent image and formatting handling, timeouts, incomplete procedure completion, malformed links, and unreliable extraction of graph-based `Cp` values.
- Explain the response: narrow task procedures, separate schema documents, verification steps, metadata conventions, and design/parameter pages.
- State the lesson: workflow quality depends on information architecture, source coverage, and quality control; a model's fluent response is not evidence of correctness.

### 4. From literature archive to VAWT concept decision

- Describe the move from broad source collection to a location-specific design problem: Boston wind data, Logan Airport selection, practical siting questions, and project criteria.
- Explain how structured wiki pages and wind-speed-binned metadata supported a comparable design space.
- Narrate the ranking process: human independent rankings, AI ranking and score calculation, persona-based weights, and human verification of the leading `vj20` and `va9` options.
- State the lesson: AI efficiently consolidated and calculated across many sources, but it could silently substitute inferred statistics or select values inconsistent with the source conclusion. Human review remained the decision authority.

### 5. AI-assisted CAD: speed versus control

- Describe Zoo/Zookeeper exploration, wiki-informed `vj20` prompting, and the comparison of short versus overly detailed prompts.
- Contrast rapid first-pass geometry generation with failures during modification, including floating or missing parts and the difficulty of repairing a model not built manually.
- Describe the productive role of OpenCode in reading KCL and debugging while the engineer developed enough model understanding to intervene.
- State the lesson: AI can accelerate a starting geometry, but design ownership requires enough CAD and code understanding to inspect, change, and validate the result.

### 6. AI-assisted CFD learning: source breadth sets the ceiling

- Describe the transition into CFD: SimScale tutorials, replication of an airfoil-validation procedure, and the first pseudo-2D validation attempts.
- Present the iterative troubleshooting sequence and the resulting learning about domain dimensionality, tip vortices, mesh resolution, and `y+`.
- Compare the bounded wiki with generic internet-connected AI: the former was more auditable; the latter could be more issue-specific but less trustworthy.
- State the lesson: a source-grounded AI system is only as useful as its source coverage and cannot replace a controlled simulation log or a matched validation benchmark.

### 7. Conclusion: A human-led workflow with explicit checks

- Summarize the first four weeks as progress from a research repository to a location-informed VAWT concept choice, initial CAD exploration, and a developing CFD-validation capability.
- Summarize the AI finding: the highest-value uses were retrieval, organization, first-pass generation, calculation, and guided learning; the weakest uses were unverified quantitative extraction, reliable formatting, state tracking across iterations, and autonomous troubleshooting.
- Close with the operating principle demonstrated by the work: use AI to widen and accelerate engineering work, but retain human source review, independent reasoning, verification, and ownership of consequential decisions.

## Evidence To Add During Drafting

- Include a concise workflow diagram showing sources, procedures, wiki pages, design ranking, CAD, CFD, and human verification.
- Include one example of a corrected AI output, such as the `Cp` interpretation issue or an AI ranking that required verification, if the supporting source and before/after record can be cited.
- Include the final design-goal statement, ranking criteria and weights, and verified comparison of `vj20` and `va9`. The daily log records that these were developed, but it does not contain all final values.
- Include CFD validation results only from the detailed study log and its cited benchmarks; this four-week log records process and provisional observations, not a completed validation conclusion.

## Uncertainty And Next Checks

The daily log is a first-person activity record, not an independent technical validation source. It supports the chronology, reported tasks, and recorded AI experience, but the final report should cite the underlying VAWT papers, wind data, CAD records, and CFD study logs for design-performance claims.

Before drafting, verify the final design goal, selected concept, ranking weights, CAD revision history, and CFD validation status against their dedicated project records.
