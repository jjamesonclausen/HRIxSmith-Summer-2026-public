---
Created: 2026-07-28
Updated: 2026-07-28
Sources:
  - "[[HRI2526]]"
  - "[[va9]]"
  - "[[va25]]"
  - "[[va32]]"
  - "[[vj20]]"
  - "[[vj28]]"
  - "[[vj6]]"
  - "[[va11]]"
Source_count: 8
tags:
  - methods
---
# VAWT Cut-In Speed Estimation Plan

> Unverified: This is a planning workflow generated for estimating a novel VAWT's cut-in speed without wind-tunnel testing. No single captured source validates this combined workflow, or establishes that it produces an accurate absolute cut-in speed. Treat its output as a design-screening estimate until it is validated against a source-matched benchmark and, ultimately, measurements.

## Source-backed starting point

- Cut-in speed is the wind speed at which a turbine begins rotating; a wind-tunnel procedure operationally defined it as the first constant rotation. (source: sources/HRI2526.md)
- Starting torque is the torque before rotation and must exceed system friction for self-starting. (source: sources/HRI2526.md)
- Positive static torque coefficient at every azimuth is used as a startup metric in one hybrid-VAWT study. (source: sources/vj20.md)
- A CFD study should save torque coefficient and, where relevant, static torque coefficient versus azimuth. (source: sources/vj20.md)
- Low-TSR startup and airfoil selection are difficult to predict with simple assumptions alone. (source: sources/va25.md)

## Generated plan

1. **Set the decision definition.** Choose whether cut-in means (a) free sustained rotation with no electrical load or (b) sustained rotation and useful electrical generation with a defined generator, controller, and load. Record the required delivered power for definition (b).
2. **Model the whole rotating assembly.** Include aerodynamic features that create drag or torque: blades, exposed shaft, struts, and deflectors. Include a resistance-torque curve for bearings, seals, gearbox, generator cogging, and the electrical load. If these are unavailable, use conservative manufacturer data or a bounded assumption and label it unverified.
3. **Screen the blade aerodynamics.** At the expected chord Reynolds-number range, generate lift and drag polars with XFOIL or sectional CFD. Extend or replace low-confidence post-stall results before using them in a rotor model; XFOIL alone is not sufficient for the rotating-blade problem. (source: sources/vj28.md)
4. **Run a low-cost rotor screen.** Feed the aerodynamic data into a DMS/DMST or related blade-element rotor model to compare geometry variants and identify likely low-speed candidates. This is a screening step only: DMST can have convergence and high-solidity prediction limits. (source: sources/va9.md)
5. **Compute static torque.** Use stationary-angle CFD snapshots at multiple azimuths and low wind speeds to obtain aerodynamic shaft torque, `T_aero(theta, V)`. Retain the complete torque-versus-azimuth curve, not just its mean.
6. **Estimate a conservative free-spin threshold.** At each wind speed, compare the minimum simulated static aerodynamic torque with the zero-speed resistance torque. The first speed satisfying `min[T_aero(theta, V)] > T_resist(0)` is a conservative estimate because it permits starting from every azimuth.
7. **Test the less-conservative case.** Simulate rotor motion from several initial azimuths, using aerodynamic torque, resistance torque, and rotor inertia. Call free-spin cut-in only when the rotor accelerates through a full revolution and approaches repeatable positive speed. > Inference: this is a proposed dynamic extension of the source-backed torque-versus-friction condition, not a validated source procedure.
8. **Check generation cut-in separately.** Apply the intended controller/generator load during the dynamic simulation. Report the lowest speed that both sustains rotation and reaches the stated electrical-power criterion; do not label the free-spin result as generation cut-in.
9. **Refine with transient rotor CFD.** For the leading designs, use a transient sliding-mesh or moving-interface model at low TSRs and save instantaneous shaft torque every angular increment. Demonstrate mesh, time-step, and revolution-to-revolution sensitivity before interpreting the result. (sources: sources/va32.md, sources/vj20.md)
10. **Report uncertainty as a range.** Vary Reynolds number, surface roughness, inlet turbulence, air density, resistance torque, electrical load, and initial azimuth. Publish the resulting free-spin and generation cut-in ranges together with all assumptions.

## Required validation gate

Before treating the estimate as predictive, reproduce a published VAWT case with matching geometry, inflow, rotation condition, coefficient definition, and averaging interval. Then demonstrate mesh and time-step sensitivity, repeatability over revolutions, and agreement with the source benchmark before changing a design variable. (source: sources/va32.md)

## Limits

- CFD is a detailed middle ground between lower-fidelity models and wind-tunnel experiments, not a replacement for measurement. (source: sources/vj6.md)
- Two-dimensional CFD misses blade-tip effects and can over-predict H-rotor performance relative to three-dimensional simulation. (source: sources/va11.md)
- The main uncertainty is near-zero-TSR aerodynamics: dynamic stall, separation, transition, and the unmeasured drivetrain resistance can materially change the estimate. (sources: sources/va25.md, sources/vj28.md)

Related: [[Wind Turbine Parameters]], [[Double-Multiple Streamtube Model]], [[Blade Element-Momentum Model]], [[XFOIL]], [[CFD]], [[VAWT CFD Study Setup Checklist]], [[Wind Tunnel Testing]]

#methods
