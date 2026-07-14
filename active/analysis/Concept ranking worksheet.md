d# Concept Ranking Worksheet

Use this page to compare the current candidate concepts before locking a baseline design.

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

## Evidence Snapshot

| Candidate                                             | Type                            | Key evidence for the criteria                                                                                                                                                                                                                                                                                                              | Main caution                                                                                                                                                                          | Source notes                                                                                                                                                                        |
| ----------------------------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Self-starting straight-bladed H-rotor Darrieus        | Original recommendation         | `va9` reports self-start at `1.25 m/s`, `Cp = 0.416` at `1.25 m/s`, and no audible noise in urban testing. The H-rotor family is easier to model than more curved or hybrid variants, and the repo already has validated parameter-study baselines for airfoil and pitch.                                                                  | The broader Darrieus family still has startup risk in general, so this path depends on making the startup-oriented blade/profile logic carry over into your chosen geometry.          | [[va9 EN0005 Self-start Darrieus VAWT]], [[H-VAWT]], [[va25 Reference H-Rotor Darrieus VAWT]], [[va26 3-Bladed H-Type VAWT]], [[Airfoil Selection for Small Straight-Bladed VAWTs]] |
| Low-TSR helical Darrieus                              | Original recommendation         | Helical layouts are repeatedly tied to smoother torque, lower noise, and lower cyclic loading. `va22` reports `3.5 m/s` startup, `100 W` rated power at `9 m/s`, and a design intentionally tuned for low-TSR urban operation.                                                                                                             | More geometrically complex to CAD and manufacture than a straight H-rotor. The strongest specific example in the repo is still centered below the target rated-speed band at `9 m/s`. | [[Helical VAWT]], [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]], [[va3 QuietRevolution QR5]]                                                                              |
| Reduced-interference hybrid                           | Original recommendation         | Hybrid logic gives a plausible startup plus efficiency compromise. The repo's strongest evidence comes from reduced-interference variants rather than classic inner-Savonius layouts: `vj20` reports `Cp = 0.486` and complete self-starting, and `vj2` reports a `22.3%` torque gain after moving the Savonius outside the Darrieus core. | Highest structural and aerodynamic complexity in this short list. Validation is weaker than for simpler rotor families, and some source numbers are context-dependent.                | [[Hybrid VAWT]], [[vj20 Proposed Hybrid VAWT]], [[vj2 Split Savonius Outside Darrieus Hybrid Wind Turbine]]                                                                         |
| Compact drag-based J-type / Savonius-derived fallback | Original recommendation         | Strong startup and simple fabrication are the main reasons to keep this class on the list. `va5` reports `3 m/s` cut-in, `35 W` rated power at `6.67 m/s`, and easy installation/maintenance. Savonius-derived concepts are also tolerant of low-speed, changing wind.                                                                     | Lower efficiency ceiling than the better lift-based options, so this class is the weakest fit to the economic-efficiency criterion.                                                   | [[va5 J-Type VAWT]], [[Savonius Turbine]], [[vj9 Scooplet-Based Savonius]]                                                                                                          |
| [[va20 Involute Rotor with Wind Flow Modifier]]       | Non-traditional specific design | The strongest `va20` case for BOS-like low wind. The modifier-assisted involute rotor reports `Cp = 0.397` at `5 m/s`, up from `0.22` for the plain involute rotor, and the diffuser tubes are reported to accelerate flow from `1.822 m/s` to `5.562 m/s`.                                                                                | Evidence is CFD-heavy, and the rectangular modifier is directional rather than omnidirectional.                                                                                       | [[va20 Involute Rotor with Wind Flow Modifier]], [[va20 Involute Blade Type Rotor]], [[Wind Flow Modifier]]                                                                         |
| [[vj20 Proposed Hybrid VAWT]]                         | Non-traditional specific design | One of the strongest unconventional performance claims in the repo: `Cp = 0.486` at `TSR = 3`, full-scale cut-in listed as `2.81 m/s`, and rated speed listed as `7.5 m/s`. Uses an inner asymmetric-airfoil H-rotor instead of a Savonius starter.                                                                                        | Startup and scaling values vary across the source, and the concept remains more complex than a simpler H-rotor baseline.                                                              | [[vj20 Proposed Hybrid VAWT]], [[Hybrid VAWT]]                                                                                                                                      |
| [[va23 50% STS-VAWT]]                                 | Non-traditional specific design | A wake-management concept rather than a startup concept. The source reports about `10%` corrected `Cp` improvement over the conventional troposkien baseline by shifting and shortening one blade to reduce blade-wake interaction.                                                                                                        | No clear low-speed startup advantage is reported, and the evidence is more about mid-to-high TSR efficiency than BOS-style startup behavior.                                          | [[va23 50% STS-VAWT]], [[Blade-Wake Interaction]]                                                                                                                                   |
| [[vj9 Scooplet-Based Savonius]]                       | Non-traditional specific design | A very manufacturable unconventional drag rotor. The source says it uses only straight lines and circular arcs of constant thickness and reports a `39%` `Cp` increase over the classical Savonius reference.                                                                                                                              | Still a Savonius-family concept, so even with improvement it likely remains below the top lift-based options on peak efficiency.                                                      | [[vj9 Scooplet-Based Savonius]], [[Savonius Turbine]]                                                                                                                               |

## Ranking Table

Scoring is `1-5`, where `5` is best relative to the current candidate set for that category. A `*` marks an informed best guess where the repo does not give a direct metric or where the row is a broader concept family rather than one single tested turbine.

| Candidate                                       | Startup ability | Efficiency / economics | Rated speed fit | Cut-out speed fit | Room for growth | CAD + manufacturability | Interesting to us | Overall notes                                                                                                              |
| ----------------------------------------------- | --------------- | ---------------------- | --------------- | ----------------- | --------------- | ----------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Self-starting straight-bladed H-rotor Darrieus  | 5               | 4                      | 4*              | 5                 | 5               | 4                       | 5*                | Strongest low-wind startup in the set, high reported `Cp`, and the cleanest path for modeling and iteration.               |
| Low-TSR helical Darrieus                        | 3               | 2                      | 5               | 3*                | 4               | 3                       | 4*                | Good urban-oriented refinement and closest known rated-speed match, but lower `Cp` and harder fabrication.                 |
| [[va20 Involute Rotor with Wind Flow Modifier]] | 3*              | 4                      | 1*              | 4*                | 4*              | 2                       | 4*                | Interesting low-wind booster concept, but the directional modifier makes it less clean for BOS-style omnidirectional use.  |
| [[vj20 Proposed Hybrid VAWT]]                   | 4               | 5                      | 3               | 3*                | 5               | 4                       | 5*                | Best reported `Cp` in the worksheet and strong self-start evidence, while still looking reasonably manageable to CAD.      |
| [[va23 50% STS-VAWT]]                           | 1*              | 3                      | 3*              | 4*                | 3*              | 4                       | 3*                | Clever wake-management design, but it is much better supported as an efficiency tweak than as a low-wind startup solution. |
| [[vj9 Scooplet-Based Savonius]]                 | 4*              | 2*                     | 1*              | 2*                | 3*              | 5                       | 3*                | Very manufacturable and clearly improved over a classical Savonius, but still limited by drag-rotor efficiency.            |

## Weighted Overall Ranking

Using your weights: startup `35%`, efficiency `35%`, CAD + manufacturability `15%`, rated speed fit `10%`, room for growth `2.5%`, and cut-out speed fit `2.5%`. The `Interesting to us` column is not included in this weighted score.

| Rank | Candidate | Weighted score (/5) | Notes |
| ---- | --------- | ------------------- | ----- |
| 1 | Self-starting straight-bladed H-rotor Darrieus | 4.40 | Highest overall mainly because it stays strong in both startup and efficiency, which dominate your weighting. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.25 | Very close second because of its top efficiency score and strong startup score, now nearly matching the straight-bladed H-rotor path. |
| 3 | [[vj9 Scooplet-Based Savonius]] | 3.08 | CAD score helps a lot here, but low efficiency and rated-speed fit keep it mid-pack. |
| 4 | [[va20 Involute Rotor with Wind Flow Modifier]] | 3.05 | Good efficiency and decent growth potential, but weak rated-speed fit and low CAD score reduce the total. |
| 5 | Low-TSR helical Darrieus | 2.88 | Good rated-speed fit, but the lower startup and efficiency scores hurt because those categories carry most of the weight. |
| 6 | [[va23 50% STS-VAWT]] | 2.48 | The weak startup score hurts most under this weighting, even though CAD and cut-out fit are better. |

## H-Type Example Ranking

This section narrows the comparison to explicit H-type / H-rotor Darrieus examples with dedicated design pages, plus `[[vj20 Proposed Hybrid VAWT]]` as the hybrid benchmark. It excludes the drag-only `va20` H-type C-blade and the HRI project-summary duplicates.

| Candidate | Startup ability - under 3 m/s | Efficiency / economics | Rated speed ~10 m/s | Cut-out speed ~20 m/s | Room for growth | CAD + manufacturing | CFD validation | Interesting to us | Overall notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [[va9 EN0005 Self-start Darrieus VAWT]] | 5 | 4 | 3* | 5 | 5 | 4 | 5* | Strongest startup evidence in the H-type set and still one of the better efficiency cases. | |
| [[va25 Reference H-Rotor Darrieus VAWT]] | 2* | 3 | 3* | 3* | 4 | 4 | 3* | Useful validated baseline, but much more of a reference model than a fully characterized product concept. | |
| [[va26 3-Bladed H-Type VAWT]] | 2* | 3* | 4* | 3* | 4 | 4 | 4* | Practical fixed-pitch H-type study with clear optimization room, but weak direct startup evidence. | |
| [[va27 Reference One-Bladed H-Type VAWT]] | 1* | 2* | 2* | 3* | 4 | 3 | 2* | Helpful for airfoil-shape exploration, but not a strong practical turbine candidate by itself. | |
| [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]] | 2* | 4 | 5 | 3* | 3* | 4 | 3* | Strong modeled efficiency and a clean `10 m/s` design point, but still a design-method case with missing startup data. | |
| [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]] | 2* | 5 | 5 | 3* | 4* | 3 | 4* | Best pure H-type efficiency case in this narrower set, with lower `AR` also presented as the better-performing option. | |
| [[va28 Windkop 5 kW H-Darrieus VAWT]] | 4* | 1* | 2* | 2* | 2* | 3 | 3* | Real deployed H-type hardware, but the reported operating results are poor and several key limits are unclear. | |
| [[vj20 Proposed Hybrid VAWT]] | 4 | 5 | 3 | 3* | 5 | 4 | 5* | Highest-performance hybrid benchmark here, with stronger startup than most pure H-types and still reasonably manageable CAD complexity. | |

## H-Type Weighted Ranking

Using the same weights as above: startup `35%`, efficiency `35%`, CAD + manufacturability `15%`, rated speed fit `10%`, room for growth `2.5%`, and cut-out speed fit `2.5%`.

| Rank | Candidate | Weighted score (/5) | Notes |
| --- | --- | --- | --- |
| 1 | [[va9 EN0005 Self-start Darrieus VAWT]] | 4.30 | Best overall because it combines the strongest startup evidence with still-strong efficiency and growth potential. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.25 | Nearly tied for first, with top-tier efficiency, good startup, and a better CAD score than previously assigned. |
| 3 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]] | 3.58 | Best pure H-type efficiency score in this set, helped by a strong rated-speed fit. |
| 4 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]] | 3.35 | Also a strong modeled H-type, but slightly behind the lower-`AR` variant. |
| 5 | [[va26 3-Bladed H-Type VAWT]] | 2.93 | Reasonable all-around research candidate, but limited by missing direct startup and whole-rotor performance data. |
| 6 | [[va25 Reference H-Rotor Darrieus VAWT]] | 2.83 | Solid benchmark reference, but not as compelling as a concept-selection target. |
| 7 | [[va28 Windkop 5 kW H-Darrieus VAWT]] | 2.50 | Real-world deployment helps, but the reported performance record in the repo is weak. |
| 8 | [[va27 Reference One-Bladed H-Type VAWT]] | 1.88 | Most useful as a simplified computational study rather than as a practical turbine concept. |

## Notes

- The rows above intentionally mix broader concept families and specific source-backed designs, because your current question is still concept selection rather than one-to-one design selection.
- The highest-overlap pair is `Reduced-interference hybrid` and [[vj20 Proposed Hybrid VAWT]]. Keep both for now if you want to compare a general hybrid path against one especially strong specific example.
- The highest-overlap pair on the drag side is `Compact drag-based J-type / Savonius-derived fallback` and [[vj9 Scooplet-Based Savonius]].
- The current BOS framing still matters while you rank: average wind speed around `4.8 m/s`, average gusts around `6.3 m/s`, and unresolved siting constraints at Logan. See [[Design goal]] and [[wiki/concepts/Airport Regulations|Airport Regulations]].

## All-Designs Top Ten - BOS-Focused Prompt

Prompt:
- Assume the goal is to choose designs that are the best fit for BOS wind conditions and the current BOS project constraints.

Weights:
- Startup `30%`
- Efficiency / economics `25%`
- Rated speed fit `15%`
- CAD + manufacturability `15%`
- Room for growth / modelability `10%`
- Cut-out speed fit `5%`

Obvious duplicate real machines were collapsed so the same turbine does not occupy multiple top-ten slots.

| Rank | Design | Score (/5) | Why |
| --- | --- | --- | --- |
| 1 | [[va9 EN0005 Self-start Darrieus VAWT]] | 4.30 | `1.25 m/s` self-start, `Cp = 0.416`, and reported stability at `25 m/s` make it the strongest match to this weighting. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.15 | `Cp = 0.486` plus explicit self-start and `2.81 m/s` full-scale cut-in keep it near the top, and the CAD burden now looks more manageable than previously scored. |
| 3 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]] | 3.60 | `cpmax = 0.475` and an explicit `10 m/s` design point score very well on efficiency, rated-speed fit, and modelability. |
| 4 | [[va3 Solwind Vertical Axis Wind Turbine]] | 3.45 | `1.5 m/s` startup, power onset at `3.7 m/s`, rated output at `10 m/s`, and slowdown around `27 m/s` make it one of the best direct fits to the operating-speed criteria. |
| 5 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]] | 3.40 | Another clean `10 m/s` H-rotor case with `cpmax = 0.464`, but slightly weaker than the lower-`AR` version. |
| 6 | [[vj19 Curved-Blade Savonius VAWT]] | 3.35 | `3 m/s` cut-in, `9 m/s` rated-speed claim, and a reported `3.5 year` simple payback keep it unusually competitive for a drag rotor. |
| 7 | [[va3 Ropatec WRE.060 WindRotor]] | 3.35 | `2 m/s` cut-in, `14 m/s` rated speed, no cut-off, and hybrid low-speed intent keep it strong, though direct efficiency evidence is thinner than the top-ranked cases. |
| 8 | [[va24 Variable-Pitch 3-Bladed NACA0015 Straight-Bladed VAWT]] | 3.10 | The reported `Cp = 0.568` peak and improved low-TSR behavior are excellent, but active pitch hurts manufacturability and the page does not give whole-turbine startup or cut-out figures. |
| 9 | [[va26 3-Bladed H-Type VAWT]] | 3.10 | Its simple fixed-pitch H-rotor layout, `7 m/s` operating case, and clear parameter-tuning room help it under this BOS-focused weighting. |
| 10 | [[va5 J-Type VAWT]] | 3.00 | `3 m/s` cut-in, `23.3%` prototype efficiency, and very easy fabrication/maintenance keep it in the top ten, but `6.67 m/s` rated speed is a weaker fit than the better lift-based options. |

Uncertainty:
- Ranks `1` and `2` are the strongest.
- Ranks `4` through `10` are less certain because many design pages are missing startup, rated-speed, or cut-out data, or mix product claims with sparse aerodynamic evidence.

## All-Designs Top Ten - Beginner-Friendly Prompt

Prompt:
- Assume the user is a complete beginner with zero experience in engineering, CAD, or simulation scale work, and the goal is simply to finish with a new VAWT design.

Weights:
- CAD + manufacturability `30%`
- Room for growth / modelability `25%`
- Startup `20%`
- Efficiency / economics `15%`
- Rated speed fit `5%`
- Cut-out speed fit `5%`

Obvious duplicate real machines were collapsed so the same turbine does not occupy multiple top-ten slots.

| Rank | Design | Score (/5) | Why |
| --- | --- | --- | --- |
| 1 | [[va9 EN0005 Self-start Darrieus VAWT]] | 4.45 | Explicit `1.25 m/s` self-start, `Cp = 0.416`, stability at `25 m/s`, and a relatively clean straight-bladed geometry make it the strongest mix of beginner-friendliness and growth potential. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.15 | It keeps complete self-starting and top-tier reported `Cp` near `0.486`, and with a `CAD = 4` score it now looks much more realistic even for a confident designer. |
| 3 | [[va5 J-Type VAWT]] | 4.00 | Its three simple J-blades, direct-drive small-scale build, `3 m/s` cut-in, and explicit easy-install/easy-maintenance positioning make it one of the clearest beginner build paths. |
| 4 | [[vj19 Curved-Blade Savonius VAWT]] | 3.90 | The drag rotor pairs strong startup-oriented behavior with explicit `3 m/s` cut-in, `9 m/s` rated-speed claim, `17 m/s` cut-out, and a reported `3.5 year` payback. |
| 5 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]] | 3.80 | This is one of the cleanest model-and-iterate pages in the repo: a simple straight-bladed H-rotor with a `10 m/s` design point and `cpmax = 0.475`, though direct startup data is missing. |
| 6 | [[va26 3-Bladed H-Type VAWT]] | 3.70 | The low-solidity fixed-pitch H-rotor is simple, practical, and explicitly framed as a modest manufacturable modification with clear room for parameter tuning. |
| 7 | [[vj9 Scooplet-Based Savonius]] | 3.65 | The page explicitly emphasizes easy manufacture from straight lines and circular arcs, while the scooplet is reported to add positive torque through the full cycle and improve `Cp` by `39%` over the classical reference. |
| 8 | [[va3 Solwind Vertical Axis Wind Turbine]] | 3.60 | It has unusually complete operating-speed data plus erection/maintenance-friendly hardware choices, but it is less clean as a modeling baseline than the academic H-rotors. |
| 9 | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]] | 3.55 | Another very modelable straight-bladed H-rotor with a clean `10 m/s` design point and `cpmax = 0.464`, just slightly weaker than the lower-`AR` case. |
| 10 | [[va25 Reference H-Rotor Darrieus VAWT]] | 3.50 | It scores well as a beginner analysis platform because it is a validated reference geometry used as a common CFD baseline, even though whole-turbine startup and speed data are sparse. |

Uncertainty:
- Ranks `1` through `4` are the strongest.
- The middle and lower part of the top ten is less stable because several otherwise-strong beginner pages do not report full startup, rated-speed, cut-out, or economics data on-page.

## All-Designs Top Ten - Expert BOS Performance Prompt

Prompt:
- Assume the user is an expert with strong CAD and simulation skills and wants to design the best possible VAWT for the Boston location.

Weights:
- Startup `20%`
- Efficiency / economics `25%`
- Rated speed fit `20%`
- Cut-out speed fit `10%`
- Room for growth / modelability `20%`
- CAD + manufacturability `5%`

Obvious duplicate real machines were collapsed so the same turbine does not occupy multiple top-ten slots.

| Rank | Design                                                         | Score (/5) | Why                                                                                                                                                                                                                           |
| ---- | -------------------------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | [[vj20 Proposed Hybrid VAWT]]                                  | 4.28       | It combines explicit self-starting, full-scale `2.81 m/s` cut-in, `7.5 m/s` rated wind speed, and the highest clearly stated top-tier `Cp` in the set (`0.486-0.491`) while still being a strong optimization platform.       |
| 2    | [[va9 EN0005 Self-start Darrieus VAWT]]                        | 4.13       | Its `1.25 m/s` field self-start, `Cp = 0.416`, and reported stability at `25 m/s` make it the best source-backed low-wind BOS performer with real high-wind survivability evidence.                                           |
| 3    | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]]                | 4.00       | This is one of the cleanest expert optimization baselines in the wiki: a simple straight-bladed H-rotor with explicit `10 m/s` design point and `cpmax = 0.475`.                                                              |
| 4    | [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]]                  | 3.95       | It keeps the same strong `10 m/s` BOS fit and high `cpmax = 0.464`, but the source itself treats the lower-`AR` sibling as the stronger performer.                                                                            |
| 5    | [[va3 Solwind Vertical Axis Wind Turbine]]                     | 3.80       | Its unusually complete operating data set, with `1.5 m/s` startup, power onset at `3.7 m/s`, rated output at `10 m/s`, and slowdown around `27 m/s`, matches Boston screening well even though aerodynamic detail is thinner. |
| 6    | [[va24 Variable-Pitch 3-Bladed NACA0015 Straight-Bladed VAWT]] | 3.72       | For an expert user, the active-pitch complexity becomes an asset because the page reports `Cp = 0.568` peak and explicit low-TSR dead-band improvement, giving it very high optimization upside.                              |
| 7    | [[vj19 Curved-Blade Savonius VAWT]]                            | 3.68       | It stays competitive because it has one of the clearest low-speed urban operating envelopes on-page: `3 m/s` cut-in, `9 m/s` rated-speed claim, `17 m/s` cut-out, and a reported `3.5 year` payback.                          |
| 8    | [[va26 3-Bladed H-Type VAWT]]                                  | 3.50       | This low-solidity H-rotor is not the highest-performing page outright, but it is a very strong expert design seed because the source gives a clean geometry, a `7 m/s` operating case, and an explicit pitch-tuning lever.    |
| 9    | [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]]        | 3.30       | It earns a spot by combining wind-tunnel validation, `3.5 m/s` starting speed, `9 m/s` design condition, and an urban low-TSR helical architecture that is directly relevant to BOS-style turbulent use.                      |
| 10   | [[va25 Reference H-Rotor Darrieus VAWT]]                       | 3.05       | It is not a finished BOS-ready machine, but it is one of the best source-backed CFD baselines in the repo, with validated reference performance around `Cp = 0.313` and strong value as an optimization starting point.       |

Uncertainty:
- The top four are the most stable.
- Ranks `5-10` are less certain because several strong optimization pages do not report full whole-turbine startup or cut-out data, while several product pages have better operating-speed data but weaker aerodynamic validation.

## EN0005 vs vj20 Across Weightings

This compares `[[va9 EN0005 Self-start Darrieus VAWT]]` and `[[vj20 Proposed Hybrid VAWT]]` across the different weighting prompts currently used in this worksheet.

| Weighting prompt | EN0005 score (/5) | vj20 score (/5) | Higher-ranked design | Why the result shifts |
| --- | --- | --- | --- | --- |
| Performance-first concept weighting: startup `35%`, efficiency `35%`, CAD `15%`, rated speed `10%`, growth `2.5%`, cut-out `2.5%` | 4.30 | 4.25 | [[va9 EN0005 Self-start Darrieus VAWT]] | EN0005 wins slightly because its startup and cut-out evidence are stronger, while vj20 wins on efficiency. |
| BOS-focused all-design weighting: startup `30%`, efficiency `25%`, rated speed `15%`, CAD `15%`, growth `10%`, cut-out `5%` | 4.30 | 4.15 | [[va9 EN0005 Self-start Darrieus VAWT]] | EN0005 still wins because BOS-fit rewards low-speed startup and proven high-wind stability more than raw peak `Cp`. |
| Beginner-friendly all-design weighting: CAD `30%`, growth `25%`, startup `20%`, efficiency `15%`, rated speed `5%`, cut-out `5%` | 4.45 | 4.15 | [[va9 EN0005 Self-start Darrieus VAWT]] | EN0005 opens the biggest gap because it combines strong startup with a simpler-looking straight-body geometry, while vj20 still carries a more involved dual-rotor layout. |
| Expert BOS performance weighting: startup `20%`, efficiency `25%`, rated speed `20%`, cut-out `10%`, growth `20%`, CAD `5%` | 4.13 | 4.28 | [[vj20 Proposed Hybrid VAWT]] | vj20 finally moves ahead when optimization headroom, rated-speed fit, and peak aerodynamic performance are weighted more heavily than simplicity. |

Takeaway:
- `[[va9 EN0005 Self-start Darrieus VAWT]]` is the safer winner under weightings that value startup, simplicity, and practical robustness.
- `[[vj20 Proposed Hybrid VAWT]]` becomes the better choice when the goal is maximum BOS-specific performance and you are comfortable handling more design complexity.
