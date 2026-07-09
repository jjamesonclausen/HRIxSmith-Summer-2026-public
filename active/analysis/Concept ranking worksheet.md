# Concept Ranking Worksheet

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

| Candidate                                             | Key evidence for the criteria                                                                                                                                                                                                                                                                                                              | Main caution                                                                                                                                                                          | Source notes                                                                                                                                                                        |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Self-starting straight-bladed H-rotor Darrieus        | `va9` reports self-start at `1.25 m/s`, `Cp = 0.416` at `1.25 m/s`, and no audible noise in urban testing. The H-rotor family is easier to model than more curved or hybrid variants, and the repo already has validated parameter-study baselines for airfoil and pitch.                                                                  | The broader Darrieus family still has startup risk in general, so this path depends on making the startup-oriented blade/profile logic carry over into your chosen geometry.          | [[va9 EN0005 Self-start Darrieus VAWT]], [[H-VAWT]], [[va25 Reference H-Rotor Darrieus VAWT]], [[va26 3-Bladed H-Type VAWT]], [[Airfoil Selection for Small Straight-Bladed VAWTs]] |
| Low-TSR helical Darrieus                              | Helical layouts are repeatedly tied to smoother torque, lower noise, and lower cyclic loading. `va22` reports `3.5 m/s` startup, `100 W` rated power at `9 m/s`, and a design intentionally tuned for low-TSR urban operation.                                                                                                             | More geometrically complex to CAD and manufacture than a straight H-rotor. The strongest specific example in the repo is still centered below the target rated-speed band at `9 m/s`. | [[Helical VAWT]], [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]], [[va3 QuietRevolution QR5]]                                                                              |
| Reduced-interference hybrid                           | Hybrid logic gives a plausible startup plus efficiency compromise. The repo's strongest evidence comes from reduced-interference variants rather than classic inner-Savonius layouts: `vj20` reports `Cp = 0.486` and complete self-starting, and `vj2` reports a `22.3%` torque gain after moving the Savonius outside the Darrieus core. | Highest structural and aerodynamic complexity in this short list. Validation is weaker than for simpler rotor families, and some source numbers are context-dependent.                | [[Hybrid VAWT]], [[vj20 Proposed Hybrid VAWT]], [[vj2 Split Savonius Outside Darrieus Hybrid Wind Turbine]]                                                                         |
| Compact drag-based J-type / Savonius-derived fallback | Strong startup and simple fabrication are the main reasons to keep this class on the list. `va5` reports `3 m/s` cut-in, `35 W` rated power at `6.67 m/s`, and easy installation/maintenance. Savonius-derived concepts are also tolerant of low-speed, changing wind.                                                                     | Lower efficiency ceiling than the better lift-based options, so this class is the weakest fit to the economic-efficiency criterion.                                                   | [[va5 J-Type VAWT]], [[Savonius Turbine]], [[vj9 Scooplet-Based Savonius]]                                                                                                          |
| [[va20 Involute Rotor with Wind Flow Modifier]]       | The strongest `va20` case for BOS-like low wind. The modifier-assisted involute rotor reports `Cp = 0.397` at `5 m/s`, up from `0.22` for the plain involute rotor, and the diffuser tubes are reported to accelerate flow from `1.822 m/s` to `5.562 m/s`.                                                                                | Evidence is CFD-heavy, and the rectangular modifier is directional rather than omnidirectional.                                                                                       | [[va20 Involute Rotor with Wind Flow Modifier]], [[va20 Involute Blade Type Rotor]], [[Wind Flow Modifier]]                                                                         |
| [[vj20 Proposed Hybrid VAWT]]                         | One of the strongest unconventional performance claims in the repo: `Cp = 0.486` at `TSR = 3`, full-scale cut-in listed as `2.81 m/s`, and rated speed listed as `7.5 m/s`. Uses an inner asymmetric-airfoil H-rotor instead of a Savonius starter.                                                                                        | Startup and scaling values vary across the source, and the concept remains more complex than a simpler H-rotor baseline.                                                              | [[vj20 Proposed Hybrid VAWT]], [[Hybrid VAWT]]                                                                                                                                      |
| [[va23 50% STS-VAWT]]                                 | A wake-management concept rather than a startup concept. The source reports about `10%` corrected `Cp` improvement over the conventional troposkien baseline by shifting and shortening one blade to reduce blade-wake interaction.                                                                                                        | No clear low-speed startup advantage is reported, and the evidence is more about mid-to-high TSR efficiency than BOS-style startup behavior.                                          | [[va23 50% STS-VAWT]], [[Blade-Wake Interaction]]                                                                                                                                   |
| [[vj9 Scooplet-Based Savonius]]                       | A very manufacturable unconventional drag rotor. The source says it uses only straight lines and circular arcs of constant thickness and reports a `39%` `Cp` increase over the classical Savonius reference.                                                                                                                              | Still a Savonius-family concept, so even with improvement it likely remains below the top lift-based options on peak efficiency.                                                      | [[vj9 Scooplet-Based Savonius]], [[Savonius Turbine]]                                                                                                                               |

## Ranking Table

Scoring is `1-5`, where `5` is best relative to the current candidate set for that category. A `*` marks an informed best guess where the repo does not give a direct metric or where the row is a broader concept family rather than one single tested turbine.

| Candidate                                       | Startup ability | Efficiency / economics | Rated speed fit | Cut-out speed fit | Room for growth | CAD + manufacturability | Interesting to us | Overall notes                                                                                                              |
| ----------------------------------------------- | --------------- | ---------------------- | --------------- | ----------------- | --------------- | ----------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Self-starting straight-bladed H-rotor Darrieus  | 5               | 4                      | 4*              | 5                 | 5               | 4                       | 5*                | Strongest low-wind startup in the set, high reported `Cp`, and the cleanest path for modeling and iteration.               |
| Low-TSR helical Darrieus                        | 3               | 2                      | 5               | 3*                | 4               | 3                       | 4*                | Good urban-oriented refinement and closest known rated-speed match, but lower `Cp` and harder fabrication.                 |
| [[va20 Involute Rotor with Wind Flow Modifier]] | 3*              | 4                      | 1*              | 4*                | 4*              | 2                       | 4*                | Interesting low-wind booster concept, but the directional modifier makes it less clean for BOS-style omnidirectional use.  |
| [[vj20 Proposed Hybrid VAWT]]                   | 4               | 5                      | 3               | 3*                | 5               | 3                       | 5*                | Best reported `Cp` in the worksheet and strong self-start evidence, with complexity as the main drawback.                  |
| [[va23 50% STS-VAWT]]                           | 1*              | 3                      | 3*              | 4*                | 3*              | 4                       | 3*                | Clever wake-management design, but it is much better supported as an efficiency tweak than as a low-wind startup solution. |
| [[vj9 Scooplet-Based Savonius]]                 | 4*              | 2*                     | 1*              | 2*                | 3*              | 5                       | 3*                | Very manufacturable and clearly improved over a classical Savonius, but still limited by drag-rotor efficiency.            |

## Weighted Overall Ranking

Using your weights: startup `35%`, efficiency `35%`, CAD + manufacturability `15%`, rated speed fit `10%`, room for growth `2.5%`, and cut-out speed fit `2.5%`. The `Interesting to us` column is not included in this weighted score.

| Rank | Candidate | Weighted score (/5) | Notes |
| ---- | --------- | ------------------- | ----- |
| 1 | Self-starting straight-bladed H-rotor Darrieus | 4.40 | Highest overall mainly because it stays strong in both startup and efficiency, which dominate your weighting. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.10 | Very close second because of its top efficiency score and strong startup score, with lower CAD score holding it back. |
| 3 | [[vj9 Scooplet-Based Savonius]] | 3.08 | CAD score helps a lot here, but low efficiency and rated-speed fit keep it mid-pack. |
| 4 | [[va20 Involute Rotor with Wind Flow Modifier]] | 3.05 | Good efficiency and decent growth potential, but weak rated-speed fit and low CAD score reduce the total. |
| 5 | Low-TSR helical Darrieus | 2.88 | Good rated-speed fit, but the lower startup and efficiency scores hurt because those categories carry most of the weight. |
| 6 | [[va23 50% STS-VAWT]] | 2.48 | The weak startup score hurts most under this weighting, even though CAD and cut-out fit are better. |

## H-Type Example Ranking

This section narrows the comparison to explicit H-type / H-rotor Darrieus examples with dedicated design pages, plus `[[vj20 Proposed Hybrid VAWT]]` as the hybrid benchmark. It excludes the drag-only `va20` H-type C-blade and the HRI project-summary duplicates.

| Candidate                                       | Startup ability - under 3 m/s | Efficiency / economics | Rated speed ~10 m/s | Cut-out speed ~20 m/s | Room for growth | CAD + manufacturing     | CFD validation    | Interesting to us                                                                                                      | Overall notes |
| ----------------------------------------------- | ----------------------------- | ---------------------- | ------------------- | --------------------- | --------------- | ----------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------- |
| [[va9 EN0005 Self-start Darrieus VAWT]]         | 5                             | 4                      | 3*                  | 5                     | 5               | 4                       | 5*                | Strongest startup evidence in the H-type set and still one of the better efficiency cases.                             |               |
| [[va25 Reference H-Rotor Darrieus VAWT]]        | 2*                            | 3                      | 3*                  | 3*                    | 4               | 4                       | 3*                | Useful validated baseline, but much more of a reference model than a fully characterized product concept.              |               |
| [[va26 3-Bladed H-Type VAWT]]                   | 2*                            | 3*                     | 4*                  | 3*                    | 4               | 4                       | 4*                | Practical fixed-pitch H-type study with clear optimization room, but weak direct startup evidence.                     |               |
| [[va27 Reference One-Bladed H-Type VAWT]]       | 1*                            | 2*                     | 2*                  | 3*                    | 4               | 3                       | 2*                | Helpful for airfoil-shape exploration, but not a strong practical turbine candidate by itself.                         |               |
| [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 2)]]   | 2*                            | 4                      | 5                   | 3*                    | 3*              | 4                       | 3*                | Strong modeled efficiency and a clean `10 m/s` design point, but still a design-method case with missing startup data. |               |
| [[vj25 1-kW Twin-Bladed H-Rotor VAWT (AR 0.4)]] | 2*                            | 5                      | 5                   | 3*                    | 4*              | 3                       | 4*                | Best pure H-type efficiency case in this narrower set, with lower `AR` also presented as the better-performing option. |               |
| [[va28 Windkop 5 kW H-Darrieus VAWT]]           | 4*                            | 1*                     | 2*                  | 2*                    | 2*              | 3                       | 3*                | Real deployed H-type hardware, but the reported operating results are poor and several key limits are unclear.         |               |
| [[vj20 Proposed Hybrid VAWT]]                   | 4                             | 5                      | 3                   | 3*                    | 5               | 3                       | 5*                | Highest-performance hybrid benchmark here, with stronger startup than most pure H-types but added complexity.          |               |

## H-Type Weighted Ranking

Using the same weights as above: startup `35%`, efficiency `35%`, CAD + manufacturability `15%`, rated speed fit `10%`, room for growth `2.5%`, and cut-out speed fit `2.5%`.

| Rank | Candidate | Weighted score (/5) | Notes |
| --- | --- | --- | --- |
| 1 | [[va9 EN0005 Self-start Darrieus VAWT]] | 4.30 | Best overall because it combines the strongest startup evidence with still-strong efficiency and growth potential. |
| 2 | [[vj20 Proposed Hybrid VAWT]] | 4.10 | Nearly as strong overall, with top-tier efficiency and good startup but more complexity. |
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
