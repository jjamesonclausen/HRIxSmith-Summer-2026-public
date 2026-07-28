# VJ20 and VA9 DOE Recommendation

> Generated response: This document records an AI-generated recommendation tailored to the VJ20 hybrid H-type VAWT baseline, the VA9 EN0005 concept, and the current Logan design brief. It is not a validated workflow, an experimentally confirmed design, or a source claim. Source-backed observations and generated inferences are identified below.

Do **not** put VJ20 and VA9 into one Box-Behnken DOE immediately. VA9's EN0005 blade and blade-end geometry are a different startup concept, not a small continuous adjustment to the VJ20 hybrid. Its reported `1.25 m/s` self-start result is from a much smaller, different rotor, so it is not evidence that it will lower VJ20 cut-in. (sources: sources/va9.md, sources/vj20.md)

For the Logan goal, prioritize low-wind utilization, manufacturability, maintenance, and a permitted height over a maximum-`Cp` result alone. (project brief: active/analysis/Design goal.md)

## Recommended Sequence

1. **Validate the VJ20 baseline first.** Reproduce its geometry and report `Cp(TSR)`, torque ripple, and static torque versus azimuth before changing anything. VJ20 reports `Cp = 0.486` at `TSR = 3` and positive static torque at all azimuths, but its reported cut-in values vary by scale and test context. (source: sources/vj20.md)

2. **Run a small concept screen, not DOE.** Keep the VJ20 dimensions, blade count, shaft, load model, and operating conditions fixed. Compare:
   - VJ20 baseline: outer `NACA0018`, inner `DU 06-W-200`.
   - VJ20 with the inner blades replaced by EN0005.
   - If needed, EN0005 inner blades with the inward blade-end orientation.

   > Inference: Putting EN0005 on the inner rotor is the cleaner first test because both the VJ20 inner rotor and VA9's EN0005 concept target startup torque. This is not a source-validated hybrid configuration.

   Judge these using minimum static torque across azimuth, estimated free-spin cut-in, `Cp` near the Logan-relevant wind range, torque ripple, and complexity. EN0005 was designed to add stopped-state downstream drag and the inward ends were reported to improve self-starting; these effects must be re-evaluated in the VJ20 wake interaction. (source: sources/va9.md)

3. **Select one architecture, then DOE the continuous geometry.** Hold turbine height at the maximum airport-permitted and manufacturable value rather than treating it as a free aerodynamic variable. Hold blade count at three inner plus three outer blades initially, because changing it also changes solidity, inertia, load smoothness, cost, and maintenance burden. (project brief: active/analysis/Design goal.md; sources: sources/vj20.md, sources/va14.md, sources/vj21.md)

4. **Use these four DOE factors for the selected architecture:**
   - Outer-blade pitch angle.
   - Inner-blade pitch angle.
   - Outer-blade chord, expressed as `c/R` or outer solidity.
   - Inner-to-outer radius ratio, equivalently the radial spacing between rotors.

   These directly affect the VJ20 geometry while preserving a reasonably interpretable and manufacturable hybrid. Pitch, chord, solidity, and rotor spacing are established VAWT performance controls. (sources: sources/vj20.md, sources/vj6.md, sources/vj21.md)

5. **Use three levels per factor and Box-Behnken.** Center each range on the validated baseline or selected EN0005 variant. Fit response surfaces for:
   - Maximize `Cp` at selected TSRs.
   - Maximize minimum static torque.
   - Minimize estimated cut-in.
   - Minimize torque ripple.
   - Apply hard constraints for airport height, manufacturability, and added-part count.

   Box-Behnken is suited to three-level, multi-factor response-surface studies; the VJ20 paper used five factors and 46 runs, while a four-factor VAWT example used 29 simulations. (sources: sources/vj20.md, sources/vj8.md)

6. **Validate the DOE model before trusting its optimum.** Check ANOVA, residuals, `R2`, and predicted-versus-new-CFD confirmation runs. Response surfaces can miss strongly nonlinear or multimodal behavior. (sources: sources/vj20.md, sources/vj6.md)

## Open Inputs

The project brief does not yet give a specific allowed turbine height, generator/load curve, target power, or wind-speed distribution at the actual Governor's Island installation point. Those determine the factor ranges and whether low cut-in should outweigh high-wind `Cp`. (project brief: active/analysis/Design goal.md)

> Uncertainty: The recommended sequence and four-factor set are generated engineering judgments. They should be reviewed after the VJ20 baseline is reproduced and after site, structural, electrical-load, and manufacturing constraints are quantified.
