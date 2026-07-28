# LLM Wiki Setup Blog Outline

#report
llm generated: 

This project did not begin with a finished AI assistant. It began with unfamiliar software, scattered VAWT research, and a need to learn fluid mechanics and design at the same time. The team built an LLM wiki to make project sources searchable, organized, and useful for learning and design decisions. Its value came from the rules, source traceability, testing, and repeated human review around it. 

## Introduction

an LLM can synthesize a large research collection much faster than a student can read every paper, but that speed can hide weak understanding or unsupported quantitative claims. State that this post documents an experiment in building a system that helps students ask better questions, rather than replacing their judgment. 

## 1. The Starting Point: A Research and Learning Problem

- We began by reviewing fluid-mechanics material, a prior capstone report, VAWT sources, and references while deciding which technical topics we needed to learn. (source: active/_Julie_daily_log.md)
- We saw the wiki as a way to combine project notes, outside research, and later experimentation in one source-grounded system that could identify knowledge gaps and support critical thinking. (source: active/_anna daily log.md)
- Early skepticism mattered: an AI system should not replace reading, source evaluation, writing, or reasoning just because it can summarize material fluently. (source: active/_anna daily log.md)

**Personal reflection prompt:** What did you hope the wiki would make easier, and what learning did you refuse to outsource?

## 2. Building the First Version of the Workflow

- Set up OpenCode, VS Code, Obsidian, GitHub, and Slack; completed the introductory workshop; and learned enough GitHub and Live Share to collaborate on one shared repository. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Wrote and revised `AGENTS.md` so the system would use project sources, cite them, mark unsupported claims, and maintain the wiki structure. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Added an eval loop and tested the wiki against the available sources instead of assuming that a polished response was reliable. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Split detailed procedures into `schema/` documents and kept broader purpose, rules, and organization in `AGENTS.md`. (source: active/_anna daily log.md)

**Possible visual:** A simple diagram showing `sources -> ingestion procedures -> wiki pages -> questions/design decisions -> verification`.

## 3. Source Ingestion Was the Real Setup Work

- The team located VAWT and fluid-dynamics sources, converted PDFs to Markdown, and added instructions for preserving figures, captions, equations, metadata, and links. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Python and PyMuPDF were added to improve PDF-image extraction, and the conversion procedure was revised after failed or incomplete conversions. (source: active/_anna daily log.md)
- The team restored original PDFs, renamed files for traceability, repaired prior source conversions, and corrected unwanted summarization, line breaks, image placement, metadata, and broken links. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- This work exposed the difference between an LLM producing an answer and a system producing a trustworthy research record: missing images, unreadable equations, formatting failures, and altered source text can damage later retrieval and analysis. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

**Reflection point:** The most time-consuming part was not asking questions. It was creating a source pipeline worth trusting.

## 4. Turning a Library Into a Design Tool

- The wiki was reorganized around concepts, methods, designs, and parameters so that the team could compare alternatives instead of storing one long summary per paper. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Tags, metadata, properties, backlinks, and Obsidian graph and Dataview features were explored to show relationships among designs, parameters, and evidence. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Metadata was refined to capture useful decision inputs, such as performance values in relevant wind-speed ranges, while recognizing that extracting quantities from figures or differing study contexts is difficult. (source: active/_anna daily log.md)
- We learned that more pages and more metadata are not automatically better; the organization has to reflect what the team needs to see when making a decision. (source: active/_anna daily log.md)

**Possible visual:** Obsidian graph, a design page, a parameter page, or a filtered base/table.

## 5. The First Payoff: Faster, More Structured Design Screening

- The wiki helped combine site wind data, airport constraints, design requirements, and research evidence into a design goal and work plan. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- The team used weighted decision tables, independently ranked designs, asked the LLM to rank them, and compared the results rather than accepting a single generated recommendation. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Personas, including an experienced performance-focused engineer and a beginner with limited CAD experience, were used to test how priorities changed the ranking. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- This process rapidly narrowed the design space and selected `va9` and `vj20` for further exploration. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

**Reflection point:** The useful output was not a final answer. It was a visible comparison structure that made assumptions, weights, and disagreements discussable.

## 6. Where the System Failed and What That Taught Us

- Source ingestion was inconsistent: models sometimes timed out, omitted figures or equations, summarized when they should have transcribed, or produced metadata and formatting errors that needed manual repair. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- The wiki could return plausible but weakly supported quantitative information. A later check found that the LLM had misreported the VJ20 cut-in speed, which could have affected design ranking. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- The team found that the LLM could infer a statistic from general background information when a paper did not directly report it, creating a response that sounded useful but did not answer the actual question. (source: active/_anna daily log.md)
- AI-generated CAD made complex geometry quickly, but changes could introduce disconnected, floating, or altered parts that were difficult to repair without understanding the underlying model. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- In CFD, adding more SimScale documentation improved general learning but did not automatically produce effective troubleshooting. Simulation outputs still required validation of geometry, mesh, dimensionality, reference data, and result controls. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

**Key lesson:** Fluency is not correctness. A wiki is only as trustworthy as its sources, procedures, checks, and the human willingness to challenge a convenient answer.

## 7. Learning With AI Instead of Sitting Behind It

- The team worried that fast synthesis and ranking could replace the slower technical struggle through which deeper understanding normally develops. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- At the same time, the wiki made it easier to ask questions across many trusted sources, request explanations, and connect concepts that might otherwise remain isolated. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- To keep learning intentional, the team used the LLM to quiz them, explain CFD concepts, identify limits of simulations, and produce more visible decision matrices and diverse alternatives. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- This reframed the goal: the deliverable was not only a turbine, but also a usable guide for future teams on how to learn with and evaluate AI tools. (source: active/_Julie_daily_log.md)

**Personal reflection prompt:** Give one example where the LLM helped you think more deeply and one where it made it tempting to stop thinking.

## 8. The Workflow Is Still Being Revised

- The team expanded the wiki into CFD, CAD, and documentation records as the project moved from literature screening to model validation. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- When the LLM's troubleshooting or ranking proved vague or unreliable, the response was not to trust it more. The team added sources, checked the underlying papers, requested explicit reasoning, considered web search when the wiki lacked information, and prepared questions for human experts. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)
- Current CFD validation difficulties remain unresolved, which is a useful example of why the system should support escalation to human expertise rather than pretend to replace it. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

## 9. Practical Takeaways for Another Student Team

1. Start with a narrow project purpose and source-grounding rules before adding many sources.
2. Treat source ingestion, metadata, figure handling, and link checking as engineering work, not administrative cleanup.
3. Build evaluations and inspect source evidence before using an AI-derived number in a decision table.
4. Use structured comparisons, independent human judgments, and multiple perspectives to make AI-assisted decisions inspectable.
5. Ask the system to teach, quiz, and expose uncertainty, not only to generate answers or rank options.
6. Keep a log of failures, corrections, and changed instructions; those are often the most transferable lessons.
7. Escalate to primary sources, documentation, or a human expert when a result matters and cannot be verified.

These recommendations are project observations from an evolving workflow, not universal rules for all LLM tools or engineering projects. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

## Closing

Return to the opening tension: the LLM wiki was most valuable when it made the team more capable of asking questions, tracing evidence, and noticing uncertainty. It was least valuable when it offered a fast, plausible answer that made verification feel unnecessary. The next phase is to keep validating the engineering work while improving the learning workflow around it. (source: active/_Julie_daily_log.md; source: active/_anna daily log.md)

## Before Publishing

- Replace the reflection prompts with personal examples in Julie's and Anna's own voices.
- Confirm what project screenshots, source figures, and company/project details can be shared publicly.
- Add screenshots of the repository structure, source-to-wiki pipeline, Obsidian organization, decision matrix, CAD workflow, and CFD validation record.
- Verify every numerical claim and named design used in the final prose against its primary source before publication.
---------------------------------------------------------------
idk how much detail we want in here - how long each section needs to be 
We did not begin this project with a finished AI research assistant. We began with little to know prior knowledge on the topic, fluid-mechanics concepts we still needed to learn, and unfamiliar tools. This projects goals have been two fold, one to design a VAWT, but also to learn and document where and how agentic tools can assist in the learning and designing process. this process was lead by first learning how to use new tools such as Opencode, VScode, Obsidian, and Github.  The first week was therefore not spent researching VAWT but rather experimenting and learning about these new tools.  
We completed the workshop, learned enough GitHub to work in one shared repository, and wrote rules for the wiki that required it to rely on project sources, cite its claims, and label unsupported material. We also built an evaluation loop instead of assuming that an answer which sounded confident was reliable. The aim was not to hand off our judgment to an LLM, but to create a source-grounded workspace that could help us find information, surface gaps, and ask better technical questions. (source: active/_anna daily log.md; source: active/_Julie_daily_log.md)

The real setup work came when we started feeding research into that system. Converting PDFs to Markdown, preserving figures and equations, maintaining metadata and links, and organizing pages around concepts, methods, designs, and parameters took repeated testing and revision. We ran into missing images, poor formatting, unwanted edits to source text, slow or inconsistent runs, and broken links; in response, we tightened the instructions, split detailed procedures into schema documents, added Python-based image extraction, and manually repaired earlier conversions. That effort made the wiki more useful, but it also made its limits clearer. A source-grounded LLM can synthesize material quickly, yet it can still produce plausible answers that need checking, and fast summarization can tempt us to skip the slower learning that engineering requires. The value of the wiki has come from treating it as an evolving research process, not as an expert whose first answer should be accepted.