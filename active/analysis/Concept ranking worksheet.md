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

| Candidate | Type | Key evidence for the criteria | Main caution | Source notes |
| --- | --- | --- | --- | --- |
| Self-starting straight-bladed H-rotor Darrieus | Original recommendation | `va9` reports self-start at `1.25 m/s`, `Cp = 0.416` at `1.25 m/s`, and no audible noise in urban testing. The H-rotor family is easier to model than more curved or hybrid variants, and the repo already has validated parameter-study baselines for airfoil and pitch. | The broader Darrieus family still has startup risk in general, so this path depends on making the startup-oriented blade/profile logic carry over into your chosen geometry. | [[va9 EN0005 Self-start Darrieus VAWT]], [[H-VAWT]], [[va25 Reference H-Rotor Darrieus VAWT]], [[va26 3-Bladed H-Type VAWT]], [[Airfoil Selection for Small Straight-Bladed VAWTs]] |
| Low-TSR helical Darrieus | Original recommendation | Helical layouts are repeatedly tied to smoother torque, lower noise, and lower cyclic loading. `va22` reports `3.5 m/s` startup, `100 W` rated power at `9 m/s`, and a design intentionally tuned for low-TSR urban operation. | More geometrically complex to CAD and manufacture than a straight H-rotor. The strongest specific example in the repo is still centered below the target rated-speed band at `9 m/s`. | [[Helical VAWT]], [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]], [[va3 QuietRevolution QR5]] |
| Reduced-interference hybrid | Original recommendation | Hybrid logic gives a plausible startup plus efficiency compromise. The repo's strongest evidence comes from reduced-interference variants rather than classic inner-Savonius layouts: `vj20` reports `Cp = 0.486` and complete self-starting, and `vj2` reports a `22.3%` torque gain after moving the Savonius outside the Darrieus core. | Highest structural and aerodynamic complexity in this short list. Validation is weaker than for simpler rotor families, and some source numbers are context-dependent. | [[Hybrid VAWT]], [[vj20 Proposed Hybrid VAWT]], [[vj2 Split Savonius Outside Darrieus Hybrid Wind Turbine]] |
| Compact drag-based J-type / Savonius-derived fallback | Original recommendation | Strong startup and simple fabrication are the main reasons to keep this class on the list. `va5` reports `3 m/s` cut-in, `35 W` rated power at `6.67 m/s`, and easy installation/maintenance. Savonius-derived concepts are also tolerant of low-speed, changing wind. | Lower efficiency ceiling than the better lift-based options, so this class is the weakest fit to the economic-efficiency criterion. | [[va5 J-Type VAWT]], [[Savonius Turbine]], [[vj9 Scooplet-Based Savonius]] |
| [[va20 Involute Rotor with Wind Flow Modifier]] | Non-traditional specific design | The strongest `va20` case for BOS-like low wind. The modifier-assisted involute rotor reports `Cp = 0.397` at `5 m/s`, up from `0.22` for the plain involute rotor, and the diffuser tubes are reported to accelerate flow from `1.822 m/s` to `5.562 m/s`. | Evidence is CFD-heavy, and the rectangular modifier is directional rather than omnidirectional. | [[va20 Involute Rotor with Wind Flow Modifier]], [[va20 Involute Blade Type Rotor]], [[Wind Flow Modifier]] |
| [[vj20 Proposed Hybrid VAWT]] | Non-traditional specific design | One of the strongest unconventional performance claims in the repo: `Cp = 0.486` at `TSR = 3`, full-scale cut-in listed as `2.81 m/s`, and rated speed listed as `7.5 m/s`. Uses an inner asymmetric-airfoil H-rotor instead of a Savonius starter. | Startup and scaling values vary across the source, and the concept remains more complex than a simpler H-rotor baseline. | [[vj20 Proposed Hybrid VAWT]], [[Hybrid VAWT]] |
| [[va23 50% STS-VAWT]] | Non-traditional specific design | A wake-management concept rather than a startup concept. The source reports about `10%` corrected `Cp` improvement over the conventional troposkien baseline by shifting and shortening one blade to reduce blade-wake interaction. | No clear low-speed startup advantage is reported, and the evidence is more about mid-to-high TSR efficiency than BOS-style startup behavior. | [[va23 50% STS-VAWT]], [[Blade-Wake Interaction]] |
| [[vj9 Scooplet-Based Savonius]] | Non-traditional specific design | A very manufacturable unconventional drag rotor. The source says it uses only straight lines and circular arcs of constant thickness and reports a `39%` `Cp` increase over the classical Savonius reference. | Still a Savonius-family concept, so even with improvement it likely remains below the top lift-based options on peak efficiency. | [[vj9 Scooplet-Based Savonius]], [[Savonius Turbine]] |

## Blank Ranking Table

Leave the scoring blank here until you decide how you want to weight each category.

| Candidate | Startup ability | Efficiency / economics | Rated speed fit | Cut-out speed fit | Room for growth | CAD + manufacturability | Interesting to us | Overall notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Self-starting straight-bladed H-rotor Darrieus |  |  |  |  |  |  |  |  |
| Low-TSR helical Darrieus |  |  |  |  |  |  |  |  |
| Reduced-interference hybrid |  |  |  |  |  |  |  |  |
| Compact drag-based J-type / Savonius-derived fallback |  |  |  |  |  |  |  |  |
| [[va20 Involute Rotor with Wind Flow Modifier]] |  |  |  |  |  |  |  |  |
| [[vj20 Proposed Hybrid VAWT]] |  |  |  |  |  |  |  |  |
| [[va23 50% STS-VAWT]] |  |  |  |  |  |  |  |  |
| [[vj9 Scooplet-Based Savonius]] |  |  |  |  |  |  |  |  |

## Notes

- The rows above intentionally mix broader concept families and specific source-backed designs, because your current question is still concept selection rather than one-to-one design selection.
- The highest-overlap pair is `Reduced-interference hybrid` and [[vj20 Proposed Hybrid VAWT]]. Keep both for now if you want to compare a general hybrid path against one especially strong specific example.
- The highest-overlap pair on the drag side is `Compact drag-based J-type / Savonius-derived fallback` and [[vj9 Scooplet-Based Savonius]].
- The current BOS framing still matters while you rank: average wind speed around `4.8 m/s`, average gusts around `6.3 m/s`, and unresolved siting constraints at Logan. See [[Design goal]] and [[wiki/concepts/Airport Regulations|Airport Regulations]].
