## [[Design goal]]s Identified
## Criteria

- Startup ability, ideally `<= 3 m/s`
- Good enough efficiency to be economic
- Rated speed around `10-15 m/s`
- Cut-out speed `>= 20 m/s`
- Room for growth: are there parameters that seem promising and plausible to model
- CADing ability plus manufacturability
- Interesting to us

## Candidate list

- Original recommendation set:
  - Self-starting straight-bladed H-rotor Darrieus
  - Low-TSR helical Darrieus
  - Reduced-interference hybrid
  - Compact drag-based J-type / Savonius-derived fallback
- Non-traditional designs discussed later:
  - [[va20 Involute Rotor with Wind Flow Modifier]]
  - [[vj20 Proposed Hybrid VAWT]]
  - [[va23 50% STS-VAWT]]
  - [[vj9 Scooplet-Based Savonius]]

## Ranking Table

Scoring is `1-5`, where `5` is best relative to the current candidate set for that category. A `*` marks an informed best guess where the repo does not give a direct metric or where the row is a broader concept family rather than one single tested turbine.
The ranking can be found in [[Concept ranking worksheet]]
## Weighted Overall Ranking

Using your weights: startup `35%`, efficiency `35%`, CAD + manufacturability `15%`, rated speed fit `10%`, room for growth `2.5%`, and cut-out speed fit `2.5%`. The `Interesting to us` column is not included in this weighted score.

## H-Type Example Ranking

This section narrows the comparison to explicit H-type / H-rotor Darrieus examples with dedicated design pages, plus `[[vj20 Proposed Hybrid VAWT]]` as the hybrid benchmark. It excludes the drag-only `va20` H-type C-blade and the HRI project-summary duplicates.

## Persona based ranking 
Prompt:
- Assume the goal is to choose designs that are the best fit for BOS wind conditions and the current BOS project constraints.
Prompt:
- Assume the user is a complete beginner with zero experience in engineering, CAD, or simulation scale work, and the goal is simply to finish with a new VAWT design.
Prompt:
- Assume the user is an expert with strong CAD and simulation skills and wants to design the best possible VAWT for the Boston location.
for all of these different prompts either VA9 or VJ20 was the top ranked design 
## EN0005 vs vj20 Across Weightings

This compares `[[va9 EN0005 Self-start Darrieus VAWT]]` and `[[vj20 Proposed Hybrid VAWT]]` across the different weighting prompts currently used in this worksheet.

## Example Tradeoff: VA9 Versus VJ20 At BOS
Had LLM look at the five year wind data and compare the potential performance of both kinds mainly to see if the higher Cp reported in VJ20 can compensate for the higher cut in speed reported. 
### Results 
- The lower VJ20 cut-in availability removes about `16.1%` of observations, but those missing winds are mostly low-speed observations and contribute little energy because available wind power scales with `V^3`. With the simplified uncapped assumption, VJ20's higher `Cp` more than covers the lost low-speed operation.
- The break-even VJ20 `Cp` in this simplified comparison is approximately `0.420`. That is, if VJ20 could maintain a `Cp` above about `0.420` over its operating wind range, it would beat VA9's `Cp = 0.416` despite the higher cut-in. This conclusion is only valid for equal swept area and equal non-aerodynamic efficiency.

## Zoo Keeper impact 
- Attempts to use zoo keeper to model va9 design showed that its additional complexity might not be worth the small increase in performance. because of the lack of specific information on geometry in the paper modeling the turbine was quite difficult, and zoo keeper seemed to be struggling more than when trying to model vj20 
- decision 