# J Design Selection Plan

## Goal

Select the best initial VAWT design direction for the project before committing to detailed modeling.

The decision should be based on:
- Boston airport wind conditions
- the evidence already collected in the wiki
- the tools available for the project
- the limited project timeline

## Available Tools

- the wiki
- ChatGPT / agent support
- Zoo Keeper, a CAD tool with integrated AI that can generate models from prompts
- standard CAD software, to be used only for troubleshooting
- email access to engineers who know more about software
- the internet
- one human project partner

## Fixed Assumption

- The location is Boston airport because there is already wind-speed and wind-direction data available for it.

## Main Principle

The initial turbine type should be selected with a short, explicit down-selection process rather than by jumping directly into modeling.

The workflow should stay site first, concept second, geometry third, validation fourth, and optimization last. (source: sources/HRI2526.md, sources/vj21.md, sources/vj6.md)

## Phase 1: Define The Decision Criteria

Before comparing concepts, define what “best” means for this project.

Use these criteria:
- ability to generate usefully in low-to-moderate wind
- self-starting / low cut-in behavior
- expected efficiency / `Cp`
- ability to tolerate changing direction and turbulence
- simplicity of geometry and manufacturability
- ease of modeling in the digital workflow
- amount and quality of evidence in the wiki
- likelihood that the project can finish credibly within the available time

Why:
- the repo repeatedly treats cut-in speed, `Cp`, TSR, swept area, and Reynolds number as first-pass metrics. (source: sources/HRI2526.md, sources/vj1.md)
- the HRI material treats low-wind power generation, low cut-in speed, and viability in turbulent urban conditions as core design concerns. (source: sources/HRI2526.md)
- the design checklist says the turbine family should be chosen based on the site and use case before geometry is locked. (source: sources/vj21.md)

### What I can help with

- build the criteria list into a weighted decision matrix
- suggest weights for each criterion
- turn the wiki into a one-page selection rubric

### What the user should do

- decide whether the project values self-starting more than peak efficiency
- decide whether the project goal is:
  - a realistic low-wind device
  - a strong simulation and report project
  - a visually compelling concept
  - or a more novel concept

## Phase 2: Limit The Candidate Set

Do not compare every concept in the wiki. Start with only these four concept families:

1. Savonius
2. straight-bladed Darrieus / H-rotor
3. helical Darrieus
4. hybrid VAWT

Why these four:
- they are the main recurring VAWT families in the repo. (source: sources/vj1.md, sources/vj2.md, sources/vj4.md, sources/vj11.md)
- the wiki already captures their main tradeoffs:
  - Savonius: strongest startup, lower efficiency
  - H-rotor Darrieus: higher `Cp`, weaker startup
  - helical Darrieus: smoother torque, more geometric complexity
  - hybrid: intended to balance startup and efficiency

### What I can help with

- pull the strongest source-backed pros and cons for each family from the wiki
- write a one-page comparison sheet

### What the user and partner should do

- agree that no additional concept family enters the decision unless one of these four clearly fails the project requirements

## Phase 3: Make A Comparison Table From The Wiki

Create one concept-comparison table with these columns:

- concept family
- typical strengths
- typical weaknesses
- cut-in / startup evidence
- `Cp` / efficiency evidence
- fit for low wind
- fit for changing direction / turbulence
- modeling complexity
- geometry complexity for Zoo Keeper
- confidence in available evidence
- notes

Why:
- annual output depends on wind distribution and the turbine power curve, not just on one average speed. (source: sources/va1.md, sources/vj13.md, sources/vj19.md)
- the design checklist and rules of thumb both imply that concept selection should be explicit and criteria-based. (source: sources/vj21.md, sources/vj28.md)

### What I want the user to do

- make the table even if it starts rough
- leave blanks where evidence is missing rather than guessing

### What I can help with

- fill the table from the wiki
- extract cut-in examples, `Cp` examples, and startup evidence into the table
- flag which claims are strong and which are weak

### Specific subtask I can do next

I can generate a concept-selection table with rows:
- Savonius
- H-rotor Darrieus
- helical Darrieus
- hybrid

and columns:
- startup
- `Cp`
- low-wind fit
- turbulence / direction fit
- modeling complexity
- best use case

## Phase 4: Use The Boston Wind Data As A Filter

Since the site is already fixed as Boston airport, use the wind data to eliminate bad starting concepts.

Check:
- how often wind is below likely cut-in thresholds
- how much time sits in the low-to-moderate operating range
- how important wind direction variability is
- whether the design should be optimized for frequent moderate flow rather than rare high-speed events

Why:
- the repo says cut-in speed should be reached a meaningful fraction of the time. (source: sources/HRI2526.md)
- annual output depends on wind distribution and direction, not just the average. (source: sources/va1.md, sources/vj13.md)
- the site-characterization pages say local wind characterization is essential before judging performance. (source: sources/vj11.md, sources/va18.md)

### What I can help with

- compute threshold-reach percentages for candidate cut-in values
- help interpret the histogram and wind distribution in terms of concept fit
- point out which concepts are at risk if low-speed startup is weak

### What the user should do

- decide whether a concept that starts poorly but has higher peak `Cp` is acceptable
- decide whether the report should prioritize real site fit or theoretical best-case efficiency

## Phase 5: Score The Concepts

After the comparison table is built, score each concept against the criteria.

Suggested weighting unless project priorities change:
- low-wind usefulness: high
- startup / cut-in: high
- direction / turbulence fit: high
- simulation tractability: medium-high
- `Cp` / efficiency: medium-high
- manufacturability / geometric simplicity: medium
- novelty: low

Why:
- the urban-wind and HRI notes emphasize low wind, changing direction, and turbulence as the central challenge. (source: sources/HRI2526.md, sources/vj11.md)
- the rules of thumb say that if self-starting matters more than top efficiency, Savonius or hybrid concepts should be considered seriously. (source: sources/vj2.md, sources/n2.md)

### What I can help with

- assign provisional scores from the wiki
- produce a ranked list
- explain why the top concept wins

### What the user and partner should do

- each score the concepts independently once
- compare scores
- discuss the biggest disagreements rather than every small one

## Phase 6: Do A Small Zoo Keeper Modeling Pilot Before Final Commitment

Before fully committing, do a very small modeling pilot on the top two concepts.

Test:
- how hard it is to generate a clean first geometry
- how controllable the dimensions are from prompts
- how many geometry errors appear
- how easy it is to make one alternate variant

Why:
- concept selection in this project is not only aerodynamic; it also has to survive the real modeling workflow
- a concept that is theoretically strong but hard to model cleanly may be a bad initial choice

### What I can help with

- help write first-pass Zoo Keeper prompts for the top two concepts
- help define what a successful modeling pilot means
- help compare concept A versus concept B after the pilot

### What the user should do

- spend only a short, fixed amount of time on this pilot
- do not optimize yet
- only check whether each concept can become a credible baseline model quickly

## Phase 7: Freeze One Initial Design Family

At the end of the process, freeze:
- one selected concept family
- one backup concept family
- one short reason for each decision

Use this output format:
- selected concept:
- backup concept:
- why selected:
- why backup:
- biggest known risk:
- first geometry variables to explore:

### What I can help with

- write the final selection memo
- convert it into a clean markdown note

## Best Division Of Labor Using The Available Tools

### User

- decide project priorities
- run the concept-scoring discussion with the project partner
- do the Zoo Keeper pilot

### Human partner

- independently score concepts
- review whether the chosen concept matches the wind regime and project scope

### Me

- mine the wiki for source-backed concept comparisons
- build the comparison matrix
- extract cut-in, `Cp`, and startup evidence
- help interpret the Boston wind data against concept types
- draft prompts for Zoo Keeper
- draft emails to engineers if outside advice is needed
- write the final concept-selection rationale

### Wiki

- source-grounded design evidence and tradeoffs

### Zoo Keeper

- rapid concept geometry generation and first-pass CAD

### Email access to engineers

- use only after the top two concepts are identified, so the question is specific and high-value

### CAD software

- use only for repair and troubleshooting after Zoo Keeper output exists

### Internet

- optional for tool-specific Zoo Keeper prompt tips, but concept selection should come from the wiki first

## Recommended Actual Selection Sequence

1. Ask for the 4-row concept comparison table from the wiki.
2. Assign weights to the criteria.
3. Ask for provisional scoring from the repo.
4. Run a small Zoo Keeper pilot on the top two concepts.
5. Freeze one concept and one backup.

This is the fastest and cleanest way to choose an initial design.

## Uncertain

- The repo strongly supports the concept tradeoffs, but it does not contain one single source saying that Boston airport wind means one exact concept is best.
- The final choice depends partly on the project goal: best real low-wind fit, easiest simulation/reporting path, or most interesting final concept.
- The repo does not contain a source-backed workflow for Zoo Keeper specifically.
