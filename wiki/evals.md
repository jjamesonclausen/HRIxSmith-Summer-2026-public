#maintenance
# Evals

The test set that keeps this wiki honest. Each eval is a question your wiki *should* answer well, plus the **known-good answer** you wrote yourself from the sources. You run them, compare, label failures, improve `AGENTS.md`, and re-test. See workshop module 04.

## Eval format

```text
### Q1: the question
- Known-good: the answer you verified from the sources, and which source(s) it comes from
- Last result: [pass / fail] — what the wiki actually answered
- Failure type: ungrounded / wrong / incomplete / anchored / sycophantic
- Fix: the AGENTS.md change (or source fix) you made in response
```

## Failure types

```text
ungrounded   claimed something no source supports (hallucination)
wrong        contradicted by a source
incomplete   missed something the sources cover
anchored     over-relied on one source, ignored another
sycophantic  agreed with a leading question instead of the evidence
```

---

## Eval Question Set:
Write 5-10 questions with a range of difficulty to test the LLM wiki.

### Q1: Explain a method that can be used to estimate wind turbine annual energy output.
- Known-good: Take annual wind data and make a histogram with bins for wind speed. Convert this to probability to determine hours of that wind speed per year, then use a turbine's power curve to determine the power produced at each wind speed. Sum across each bin.
- Last result: [pass]
	  Use the bin method.
	1. Collect long-term wind-speed data at the turbine site.
	2. Group the wind speeds into bins, often 1 m/s wide.
	3. For each bin, find how often that wind speed occurs.
	4. Convert that frequency to annual hours.
	5. Multiply annual hours by the turbine’s power at that wind speed from its power curve.
	6. Sum all bin contributions to get annual energy output.
	This works because it combines the site’s wind distribution with the turbine’s performance curve. 
	(source: sources/va1.md, wiki/methods/Bin Method.md, wiki/methods/AEO Calculation.md)
- Failure type: n/a
- Fix: n/a

### Q2: What are the three main broad categories of VAWTs? 
- Known-good: Darrius (lift), Savonius (drag), hybrid
- Last result: [pass]
	Darrieus (lift-based), Savonius (drag-based), and hybrid VAWTs. 
	(source: sources/HRI2526.md)
- Failure type: n/a
- Fix: n/a

### Q3: What is a limitation of binning for AEO calculations? What is the trade off?
- Known-good: Can hide small changes in wind speed, but if bins are too small it can show too much noise and give unreliable results.
- Last result: [pass]
	Binning smooths out fine-grained wind variation and can miss directional effects and turbulence. The tradeoff is:
	- Smaller bins: more detail, but noisier and less reliable statistics.
	- Larger bins: more stable statistics, but less detail. 
	(source: sources/va1.md, wiki/methods/Bin Method.md)
- Failure type: n/a
- Fix: n/a

### Q4: What are the advantages and disadvantages of Darrius turbines? Explain in a short paragraph.
- Known-good: very efficient (30-40%) but can't self start in low wind conditions, best in higher wind, mention structural stress and noise from turbulent wind loading
- Last result: [pass]
	- Darrieus turbines are lift-based VAWTs that can be fairly efficient and perform better at higher wind speeds, with TSR greater than 1. Their main disadvantage is poor self-starting, and their blades experience changing angles of attack that create dynamic loading, which can add mechanical stress and make them less effective in low or highly variable winds. (source: sources/HRI2526.md, sources/va1.md)
- Failure type: incomplete, we'd prefer a little more explanation of why
- Fix: **julie is working on it**

### Q5: What information is most critical for a very robust and accurate AEO estimation?
- Known-good: Good wind data! should be in the proposed turbine location, and ideally CFD should be done to look at building effects and turbulence and wind direction.
- Last result: [fail]
	- Accurate, site-specific wind data at the actual turbine location and height. If the wind input is wrong, the AEO estimate will be wrong no matter how good the binning or power curve is. (source: sources/va1.md, wiki/methods/AEO Calculation.md)
- Failure type: incomplete, should specify that wind conditions can vary greatly over short distances especially in urban conditions where buildings can create turbulence and quick changes in direction of wind
- Fix: n/a

### Q6: What is the ideal overlap ratio for a Savonious VAWT? 
- Known-good: Ideal overlap ratio for a Savonious VAWT lies within a range of 0.1 t 0.30. One study found that for winds under 4 m/s the ideal OR was 0.15 and for winds greater OR of 0.3 was ideal. There is no widespread agreement on the ideal OR however 0.15 is a frequently cited number. 
- Last Result: [pass]
	-  Around 0.15 is the commonly cited target. One source says 0.15 is suitable below 4 m/s, while 0.30 is best above 4 m/s, so there is no single universal ideal. (source: sources/n2.md)

- Failure type: N/A
- Fix: N/A

### Q7: I know that egg beater type Darrius VAWTs are less structurally sound than H-type or helical ones. Why is that?
- Known-good: That is incorrect. Eggbeater type VAWTs are actually the most structurally stable due to their curved blades which are connected directly to the rotor at the top and bottom. This ensures the blades are only in tension and experience minimal bending and shearing. H-type VAWTs on the other hand experience a great deal of mechanical loading in turbulent wind conditions because their blades are connected to the rotor via long beams which are subject to bending and twisting in rough winds. **I'm unsure where I read this info so there's a slight chance it will fail bc it actually isn't in the sources we gave it, ill come back to this** 

- Last Result: [pass/fail]
	- The sources do not support that claim.
	What they do say is:
	- Eggbeater, H-type, and helical Darrieus turbines differ in blade curvature, which affects self-starting, torque consistency, and manufacturability. (source: sources/HRI2526.md)
	- H-type and helical variants are discussed as design alternatives, but no source here says eggbeater is inherently less structurally sound. (source: sources/HRI2526.md)
	So the safest answer is:
	- I can’t justify “less structurally sound” from these sources.
	- The evidence here only supports differences in geometry and operating behavior, not a structural ranking. (source: sources/HRI2526.md, sources/vj1.md)
	Uncertain:
	- If you want, I can search other source files for a direct structural comparison.
- Failure type: n/a
- Fix: n/a

### Q8: What is the best kind of VAWT?
- Known-good: There is no one best kind of VAWT, each type of VAWT has its advantages and disadvanges. Certain types are better suited for a project dependent on conditions such as wind speed, location, size, cost, and wind variability. 
- Last Result: [pass]
	- No single source says there is one universal best VAWT.
	- For electricity generation efficiency/power, the sources favor Darrieus-type, especially helical Darrieus, because lift-based VAWTs can extract more power than drag-type Savonius turbines.  
	- For simplicity and ruggedness, the sources favor Savonius, but it is less efficient.
	So if you mean best overall for power output, the answer is helical Darrieus.  
	Uncertain: “best” depends on whether you care about efficiency, reliability, low-speed operation, or maintenance.
- Failure type: incomplete
- Fix: tightened AGENTS page to have it give aswers with more reasoning behind them rather than just spitting out facts. 

### Q9: Is adding surface texture similar to golf-ball dimples to the blades of an H-type VAWT a viable method for improving efficiency or start-up ability?
- Known-good: It is unlikely that adding surface texture would improve the efficiency or start-up ability of an H-type VAWT since doing so would increase skin drag and not provide a meaningful decrease in form drag. Surface texture like the dimples on golf balls is useful to promote a turbulent boundary layer around a blunt object which serves to drastically reduce pressure (form) drag which is the primary source of drag for blunt objects. The airfoil blades of an H-VAWT are very aerodynamic as is, so the skin drag over their surface is more of an issue than form drag, so surface texture probably wouldn't help. However, it is possible that surface texture could be used to reduce parasitic drag in Savonius VAWTs but this is an unverified claim. Additionally, much finer texturing such as microscopic ridges similar to shark skin could serve to reduce skin drag and therefore would improve the efficiency of an H-type VAWT.

- Last Result: [pass/fail]
	- Not based on the sources here.
	What the sources support:
	- The H-type optimization work improves performance by changing airfoil shape with CST, especially leading-edge curvature and mounting angle. (source: sources/va2.md)
	- That study reports higher Cp, less pressure drag, and weaker flow separation after shape optimization. (source: sources/va2.md)
	What the sources do not support:
	- No source here shows golf-ball-like dimples or surface texturing on H-type blades.
	- No source here claims that roughening an H-type blade improves start-up or efficiency.
	So the source-grounded answer is:
	- Not a demonstrated or supported method in this wiki.
	- The supported direction is airfoil-shape optimization, not dimpling. (source: sources/va2.md)
- Failure type: probably more a failure in my question asking. but we know it won't make stuff up so thats nice
- Fix:


### Q10: 