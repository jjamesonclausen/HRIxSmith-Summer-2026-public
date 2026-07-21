# LLM Blog Outline: Julie's First Four Weeks

## Possible Title

Building a VAWT Research Workflow with an LLM: Four Weeks of Learning, Design, and CFD

## Core Story

This post can follow the shift from entering the project with limited fluid-mechanics and VAWT background to building an LLM-supported research system, using it to narrow turbine concepts, and beginning to validate designs through CAD and CFD. The important thread is not just what the team produced, but how the tools changed the learning and decision-making process. (source: active/_Julie_daily_log.md)

## 1. Starting With the Problem and the Fundamentals

- Learned the fluid-mechanics and VAWT topics needed for the project by reviewing prior notes, lecture material, recorded lectures, a previous capstone report, its appendix, and cited references. (source: active/_Julie_daily_log.md)
- Began researching VAWT concepts and locating technical sources on VAWTs and fluid dynamics. (source: active/_Julie_daily_log.md)
- Identified an early project need: create a source-grounded system that could help organize and retrieve research rather than relying on scattered documents. (source: active/_Julie_daily_log.md)

## 2. Building an LLM-Supported Research Environment

- Set up OpenCode, VS Code, GitHub, and Obsidian, then completed a workshop to learn the basic workflow. (source: active/_Julie_daily_log.md)
- Learned collaborative GitHub workflows, including asynchronous work and live collaboration. (source: active/_Julie_daily_log.md)
- Developed the project rules and schema for an LLM wiki, including procedures for converting PDFs to Markdown while retaining referenced images. (source: active/_Julie_daily_log.md)
- Started feeding the system VAWT and fluid-dynamics sources, testing the LLM on that material, and refining the rules and evaluation approach. (source: active/_Julie_daily_log.md)
- Encountered practical limitations early: PDF conversion, image cropping and placement, formatting, and the risk that the LLM could edit raw source text incorrectly. (source: active/_Julie_daily_log.md)

## 3. Improving the Wiki Instead of Treating It as Finished

- Recovered and renamed original PDFs so source Markdown files could be traced back to their originals. (source: active/_Julie_daily_log.md)
- Corrected earlier source summaries, line breaks, image placement, metadata, and broken links. (source: active/_Julie_daily_log.md)
- Clarified the conversion schema so incomplete publication dates were recorded as fully as available rather than omitted. (source: active/_Julie_daily_log.md)
- Expanded the wiki structure with design and parameter sections and relevant tags. (source: active/_Julie_daily_log.md)
- Explored how Obsidian links, tags, Dataview, and possible equation pages could make connections among concepts, parameters, and design decisions more useful. (source: active/_Julie_daily_log.md)
- Processed additional sources while troubleshooting incomplete images, equations, metadata, and unwanted source summarization during ingestion. (source: active/_Julie_daily_log.md)

## 4. Bringing Site Constraints Into the Design Process

- Selected an airport location and gathered minute-by-minute wind data, including wind speed, direction, and gust information. (source: active/_Julie_daily_log.md)
- Created a wind-speed histogram and used the LLM to identify location advantages, tradeoffs, and parameters worth optimizing. (source: active/_Julie_daily_log.md)
- Investigated airspace regulations and translated the airport context into design constraints, including height, visibility, scale, and the reduced importance of noise. (source: active/_Julie_daily_log.md)
- Defined a design goal and began screening turbine concepts against the location and project constraints. (source: active/_Julie_daily_log.md)

## 5. Narrowing the VAWT Design Space

- Researched candidate VAWT designs and added an H-type Darrieus VAWT source to support the screening process. (source: active/_Julie_daily_log.md)
- Built weighted categories to rank concepts and compared personal rankings with LLM-assisted rankings. (source: active/_Julie_daily_log.md)
- Used multiple decision perspectives, including an experienced professional and a novice designer with limited engineering or CAD experience, to challenge a single ranking method. (source: active/_Julie_daily_log.md)
- Chose the H-type direction, then selected the `va9` and `vj20` designs as the two designs to take forward after repeated rankings produced the same top results. (source: active/_Julie_daily_log.md)
- Documented prompts intended to guide ZooKeeper-based CAD modeling and studied the selected source designs more closely. (source: active/_Julie_daily_log.md)

## 6. Learning CAD and Beginning CFD Validation

- Explored ZooKeeper and its GitHub connection, tutorials, parametric-design examples, and basic turbine-like geometry creation. (source: active/_Julie_daily_log.md)
- Tested initial turbine modeling but found that AI-directed edits could alter acceptable geometry when changing unrelated elements; requested code-level change reporting to make manual revision possible. (source: active/_Julie_daily_log.md)
- Used new models to compare power coefficient and cut-in-speed information for the two selected designs and documented broader VAWT basics. (source: active/_Julie_daily_log.md)
- Learned SimScale through tutorials, simple geometry tests, practice simulations, a random-airfoil setup, and examples of VAWT CFD studies. (source: active/_Julie_daily_log.md)
- Ran early simulations and found that result verification and reproducing the prior team's setup were difficult. (source: active/_Julie_daily_log.md)
- Shifted toward airfoil validation, including NACA 0018 and NACA 0012 cases, changing angle of attack, lift direction, mesh settings, and two-dimensional modeling assumptions. (source: active/_Julie_daily_log.md)
- Improved an airfoil result by modeling a two-dimensional plane, but recognized remaining lift and validation uncertainty rather than treating the improvement as proof of correctness. (source: active/_Julie_daily_log.md)

## 7. What the LLM Changed About Learning

- The LLM wiki made it possible to compare evidence across many sources quickly and ask targeted questions on demand. (source: active/_Julie_daily_log.md)
- Weighted decision tables and multiple perspectives made design selection more transparent than a single unstructured recommendation. (source: active/_Julie_daily_log.md)
- The work exposed a learning risk: rapid synthesis can bypass the productive struggle that normally forces deeper technical understanding. (source: active/_Julie_daily_log.md)
- The project reframed its deliverable as a future-team guide for using LLMs and AI tools to learn and support an engineering project, not only as a final-turbine outcome. (source: active/_Julie_daily_log.md)
- The team responded by making learning more intentional: asking the LLM to teach and quiz them on CFD, examining what simulations can and cannot reliably show, requesting diverse answers, and seeking more visible decision logic. (source: active/_Julie_daily_log.md)

## 8. Challenges and Honest Lessons

- LLM outputs required continuous checking because source ingestion and formatting could fail in subtle ways. (source: active/_Julie_daily_log.md)
- CAD-generation tools were promising for fast iteration but raised concerns about whether the underlying model structure would remain reliable for later edits. (source: active/_Julie_daily_log.md)
- CFD work required more than accepting tool output: setup choices, geometry, dimensionality, mesh, reference data, and interpretation all affected whether a result could be trusted. (source: active/_Julie_daily_log.md)
- The post should present the process as an experiment in AI-assisted engineering learning, not as evidence that the LLM independently made validated engineering decisions. (source: active/_Julie_daily_log.md)

## Closing Direction

- Return to the central question: how can AI accelerate research and iteration without letting the student become a passive user of the tool?
- Preview the next phase: validate the CFD workflow, continue refining the chosen VAWT designs, and turn the lessons from the process into a practical guide for future teams.

## Details to Add Before Publishing

- Add screenshots or diagrams of the wiki structure, decision matrix, wind-data histogram, early ZooKeeper model, and SimScale validation workflow.
- Confirm which project details, software screenshots, and external sources may be shared publicly.
- Add personal reflections and transitions in Julie's own voice; this outline preserves the documented project work but is not a finished narrative.
