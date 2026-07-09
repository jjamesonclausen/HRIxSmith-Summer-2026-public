---
Created: 2026-07-06
Updated: 2026-07-08
Sources:
  - "[[vj8]]"
  - "[[vj4]]"
  - "[[va14]]"
  - "[[va15]]"
  - "[[vj15]]"
  - "[[vj17]]"
  - "[[vj18]]"
  - "[[vj21]]"
  - "[[vj22]]"
  - "[[vj24]]"
  - "[[vj25]]"
  - "[[vj27]]"
  - "[[vj11]]"
  - "[[va8]]"
  - "[[va9]]"
  - "[[vj28]]"
Source_count: 16
tags:
  - concepts
---
## VAWT Aerodynamic Design Parameters

These are the main geometry knobs the sources repeatedly treat as design variables.

- Tip Speed Ratio (TSR) is one of the core performance controls. (source: sources/HRI2526.md, sources/vj1.md)
- Blade pitch angle is a major tuning variable. (source: sources/vj8.md)
- Relative airfoil thickness affects performance and should be checked alongside pitch. (source: sources/vj8.md)
- Rotor spacing matters in contra-rotating arrangements. (source: sources/vj8.md)
- Included angle is another tuning variable in the contra-rotating study. (source: sources/vj8.md)
- Blade number, camber line, and blade inclination are key architectural choices for small VAWTs. (source: sources/vj4.md)
- Solidity changes the balance between efficiency and starting behavior. (source: sources/vj1.md, sources/HRI2526.md)
- The va14 study adds that increasing solidity lowers optimal tip-speed ratio and that a simple `sλ^3` combination keeps `λopt` nearly invariant across its tested H-type cases. (source: sources/va14.md)
- Swept area, Reynolds number, and starting torque remain basic sizing parameters. (source: sources/HRI2526.md, sources/vj6.md)
- The va15 experiment adds direct evidence that solidity, blade profile, pitch angle, surface roughness, and aspect ratio are coupled startup/performance knobs for a small H-Darrieus turbine. (source: sources/va15.md)
The vj15 study adds that harmonic pitch amplitude is another coupled control knob, and that the best case depends on the pitch function as well as the amplitude. (source: sources/vj15.md)
The vj17 study adds CST curvature coefficients as airfoil-shape design knobs for a Savonius rotor, with eight variables optimized in the final run. (source: sources/vj17.md)
- The vj18 review broadens the design-knob list to include variable pitch law, flap angle, Gurney-flap geometry, blade morphing, mass-block placement, suction/blowing slots, and swept-area change. (source: sources/vj18.md)
- It also reports that the best-performing variable schemes are not always the simplest mechanically, so aerodynamic gains need to be weighed against actuator and materials complexity. (source: sources/vj18.md)
- The vj21 design-guide paper adds chord-radius ratio, strut profile, and blade aspect ratio as explicit aerodynamic knobs for smaller fixed-pitch SB-VAWTs. (source: sources/vj21.md)
- It says high solidity helps low-speed torque but raises cost, narrows the efficient `lambda` band, and increases inertia, while low aspect ratio should be avoided if acceptable peak efficiency is the goal. (source: sources/vj21.md)
- It also notes that large `c/R` worsens flow-curvature effects and therefore tends to hurt blade aerodynamic efficiency. (source: sources/vj21.md)
- The vj22 simulation paper adds a direct low-wind comparison between `NACA 0012` and `NACA 0015`, using `Cl`, `Cd`, and `Cl/Cd` to choose the better rotor airfoil. (source: sources/vj22.md)
- It also links blade count to TSR and solidity explicitly, reporting `TSRmax` values of `4.2`, `2.5`, and `1.6` for `3`, `5`, and `8` blades and corresponding solidity values of `0.51`, `0.85`, and `1.36`. (source: sources/vj22.md)
- The vj24 paper adds inverse-tailored airfoil surface velocity distribution as a design knob for low-speed straight-bladed Darrieus rotors, with the transition-ramp shape used to influence low-Re separation-bubble behavior. (source: sources/vj24.md)
- It keeps maximum thickness at `18%` chord and zero pitching moment as design constraints while changing the effective surface `alpha*` distribution to reach its power target. (source: sources/vj24.md)
- The vj25 paper adds rotor aspect ratio `AR = h/R` as a first-order H-rotor sizing knob, linking lower `AR` to larger radius and chord, higher Reynolds number, and slightly higher `Cp` in its `1 kW` `NACA 0018` case study. (source: sources/vj25.md)
- It also makes the tradeoff explicit that lower `AR` reduces rotational speed while increasing structural thickness and rotor inertia. (source: sources/vj25.md)
- The `vj28` paper adds a reusable blade-airfoil-selection framework for small fixed-pitch SB-VAWTs, listing nine desired aerodynamic traits and four corresponding geometric features. (source: sources/vj28.md)
- It specifically highlights camber, thickness, leading-edge radius, and trailing-edge sharpness as coupled airfoil-shape knobs rather than details that can be tuned one at a time in isolation. (source: sources/vj28.md)
- The `vj27` review adds wind-deflector geometry and placement as explicit passive design knobs, covering flat plates, airfoil-shaped deflectors, kite-shaped compound layouts, inclination angle, upstream spacing, and deflector length. (source: sources/vj27.md)
- It says these deflector variables matter because they redistribute upstream flow, suppress returning-blade penalty, and can materially raise both torque coefficient and power coefficient when tuned correctly. (source: sources/vj27.md)
- The VAWT review gives Savonius TSR around 0.6-1.2, Darrieus TSR around 2.5-5.0, and emphasizes that the optimum shifts with solidity. (source: sources/vj11.md)
- It treats blade profile, pitch angle, blade count, and chord Reynolds number as the main coupled design knobs. (source: sources/vj11.md)
- It notes that low-solidity rotors push peak Cp to higher TSR, while high-solidity rotors self-start better but suffer more blade-wake interaction. (source: sources/vj11.md)
- The va8 patent treats asymmetrical blade profile geometry as a startup-torque design knob, specifying upper/lower surface path difference of 20% of chord, chord-line-to-bottom-surface path difference of 3% of chord, and maximum-thickness-to-chord ratio of 11.5%. (source: sources/va8.md)
- The same patent fixes the angle between blade chord line and horizontal beam at 25 degrees, and its wind tunnel observations show maximum lift coefficient near a 25-degree angle of attack for the tested profile. (source: sources/va8.md)
- The va14 paper says blade number has little effect on peak `Cp` near `λopt` at fixed `Rec`, but still changes load fluctuation scale, wake behavior, and practical design tradeoffs. (source: sources/va14.md)
- The va9 paper treats blade-profile shape as a self-start design knob: the EN0005 upper surface is high-lift, the first 20% of the lower surface is high-lift, and the remaining lower surface ends in a cup form that increases stopped-position drag in the downstream zone. (source: sources/va9.md)
- The same paper compares EN0005 with NACA0018, NACA0020, NACA4418, and NACA4420 using pressure-coefficient contributions to tangential and normal force. (source: sources/va9.md)
- It reports EN0005 has better lift coefficient between -60 and -10 degrees, lower drag coefficient in that same interval, and a higher moment-coefficient peak between -30 and 0 degrees than the compared profiles. (source: sources/va9.md)

![Source figure](va8-fig4.jpg)
Original caption: Figure 4: Cross sectional view showing the blade having the asymmetrical airfoil profile. [[va8|Source]]
![Source figure](va8-fig5.jpg)
Original caption: Figure 5: Relation between lift coefficient and angle of attack. [[va8|Source]]
![Source figure](va9-fig7.jpg)
Original caption: Fig. 7. Cpr contribution to Tpr. [[va9|Source]]
![Source figure](va9-fig9.jpg)
Original caption: Fig. 9. Lift coefficient. [[va9|Source]]
![Source figure](va14-fig3.jpg)
Original caption: Fig. 3. Contours of power and thrust coefficients in l e s space for 2-, 3- and 4-bladed VAWTs with the same Rec at identical l e s positions. Each contour plot is based on 48 simulations (TI = 5%). [[va14|Source]]

Related:
- [[Wind Turbine Parameters]]
- [[Rules of Thumb]]
- [[Wind Tunnel Testing]]
- [[Double-Multiple Streamtube Model]]
- [[Variable VAWT Design]]
- [[va9 EN0005 Blade Profile]]
- [[va14 Solidity]]
- [[va14 Blade Number]]
- [[va15 Solidity]]
- [[va15 Blade Pitch Angle]]
- [[vj24 Blade Airfoil]]
- [[vj25 Rotor Aspect Ratio]]
- [[Wind Deflector]]
- [[vj27 Wind Deflector Shape]]
- [[vj27 Wind Deflector Position and Orientation]]
