# Evals

The test set that keeps this wiki honest. Each eval is a question your wiki *should* answer well, plus the **known-good answer** you wrote yourself from the sources. You run them, compare, label failures, improve `AGENTS.md`, and re-test. See [workshop module 04](../workshop/04-evaluation-loop.md).

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

## Worked example (replace with your own)

### Q1: Explain a method that can be used to estimate wind turbine annual energy output.
- Known-good: Take annual wind data and make a histogram with bins for wind speed. Convert this to probability over a year and use a turbine's power curve to determine the power produced at each wind speed. Sum across each bin.
- Last result: [pass]
	  A common method is:
		- Use the bin method to group wind speed data into intervals (e.g., 1 m/s bins)
		- For each bin:
			- Determine the probability of that wind speed
			- Convert to hours per year (× 8760)
			- Multiply by the turbine’s power output at that speed (from its power curve)
		- Sum across all bins to get total Annual Energy Output (AEO)  
		(source: sources/g1.md)
- Failure type: n/a
- Fix: n/a

### Q2: What are the three main broad categories of VAWTs? 
- Known-good: Darrius (lift), Savonius (drag), hybrid
- Last result: [pass]
	1. Darrieus (lift-based)  
	2. Savonius (drag-based)  
	3. Hybrid turbines (combine lift and drag concepts)  
	(source: sources/n1.md)
- Failure type: n/a
- Fix: n/a

### Q3: What is a limitation of binning for AEO calculations? What is the trade off?
- Known-good: Can hide small changes in wind speed, but if bins are too small it can show too much noise
- Last result: [pass]
	Limitation:
	- Binning smooths out fine-grained variations in wind, including turbulence and short-term fluctuations  
	- It also does not capture directional effects  
	(source: sources/g1.md)
	Tradeoff:
	- Smaller bins → higher resolution but less data per bin (noisier, less reliable statistics)
	- Larger bins → more stable statistics but loss of detail
- Failure type: _didn't cite a source for the tradeoff
- Fix: under Answering Questions
	- Cite the source files behind **every part** of your answer.

### Q4: What are the advantages and disadvantages of Darrius turbines? Explain in a short paragraph.
- Known-good: very efficient (30-40%) but can't self start in low wind conditions, best in higher wind, mention structural stress and noise from turbulent wind loading
- Last result: [pass]
	- Darrieus turbines are lift-based and offer higher aerodynamic efficiency (typically ~30–40%), allowing them to generate more power at higher wind speeds and achieve higher tip speed ratios. However, their main disadvantage is poor self-starting capability, meaning they often require external assistance to begin rotating. They also experience dynamic loading due to changing angles of attack during rotation, which can introduce mechanical stress. As a result, while they are more efficient than drag-based designs, they are more complex and less effective in very low or highly variable wind conditions.  
		(source: sources/n1.md, sources/g1.md)
- Failure type: n/a
- Fix: n/a

### Q5: What information is most critical for a very robust and accurate AEO estimation?
- Known-good: Good wind data! should be in the proposed turbine location, and ideally CFD should be done to look at building effects and turbulence and wind direction.
- Last result: [pass]
	- The most critical input is accurate, site-specific wind data at the actual turbine location.
		This is because:
		- AEO depends directly on the wind speed distribution
		- Errors in wind data (e.g., wrong height, wrong location, ignoring building effects) lead to systematically incorrect energy estimates
		- No improvement in binning or modeling can compensate for incorrect input data  
		(source: sources/g1.md)
- Failure type: n/a
- Fix: n/a