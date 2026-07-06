---
Created:
Updated: 2026-07-06
Sources:
- [[HRI2526]]
- [[va15]]
- [[va8]]
- [[va12]]
- [[va11]]
- [[va9]]
- [[va22]]
Source_count: 7
Tags:
- methods
---
## Wind Tunnel Testing

Experimental method used to evaluate turbine performance at small scale. (source: sources/HRI2526.md)

![Source figure](../../images/hri2526-fig12.jpg)
Original caption: Fig. 12. Wind Tunnel Testing Setup [[HRI2526|Source]]

Setup:
- Small-scale 3D printed turbines mounted on a vertical rod with bearings. (source: sources/HRI2526.md)
- Prototypes were about 5 in tall x 4.5 in wide for comparable swept area. (source: sources/HRI2526.md)
- Wind speed increased incrementally in 0.1 Hz steps starting around 0.4 Hz. (source: sources/HRI2526.md)

Measurements:
- No spin, intermittent spin, constant spin. (source: sources/HRI2526.md)
- Cut-in speed defined as first constant rotation. (source: sources/HRI2526.md)
- Angular velocity measured via tachometer. (source: sources/HRI2526.md)
- The Darrieus with Savonius Compartments concept was dropped after it failed to cut in. (source: sources/HRI2526.md)
- The va8 patent used a 3.6 m long, 0.36 m square wind tunnel with a 2-hp fan and reports a 13 m/s airflow for lift-coefficient testing of its blade profile at different angles of attack. (source: sources/va8.md)
- That source used the lift-coefficient curves to support a 25-degree blade mounting angle, but the result is a single patent example rather than a broadly validated experimental trend. (source: sources/va8.md)
- The va9 field tests used urban scenarios and a controlled wind-tunnel environment to evaluate a Darrieus VAWT prototype with sensor modules including an anemometer, infrared rotation counter, voltage sensor, and current sensor connected through Arduino and ZigBee data collection. (source: sources/va9.md)
- The va9 prototype self-started at 1.25 m/s and remained stable under a 25 m/s wind-tunnel stress test. (source: sources/va9.md)
- Its noise test reports identical measured values when stopped and running at 0, 1, 2, and 3 m distance for 2.5 m/s and 5.0 m/s wind speeds. (source: sources/va9.md)
- The va11 wake review adds wind-tunnel wake measurements out to about 10D downstream for H-rotor VAWTs, including streamwise and vertical wake-velocity mapping and paired-turbine wake comparisons. (source: sources/va11.md)
- It also notes a reviewed case with about 24.7% blockage ratio, explicitly flagging blockage as a wind-tunnel interpretation issue for VAWT wake studies. (source: sources/va11.md)
- The va12 pair-study used an open-circuit wind tunnel with a 2.06 m by 1.97 m test section, a maximum rotor blockage ratio of 3.1%, and two modified 5-bladed commercial VAWTs. (source: sources/va12.md)
- Instead of direct electrical power as the main comparison metric, it used normalized free-spinning rotational rate as a lower-noise surrogate for turbine performance. (source: sources/va12.md)
- The va15 experiment adds time-varying startup traces, repeated runs, optical rotational-speed measurements, and spin-down calibration of system resistance torque before computing blade torque and `Cp`. (source: sources/va15.md)
- The va22 paper adds a large closed-loop wind-tunnel case with a `5 m x 2.5 m x 20 m` test section, inflow turbulence intensity below `1.5%`, and flow nonuniformity below about `±2%`. (source: sources/va22.md)
- That source measures starting wind speed by increasing wind speed in `0.5 m/s` steps with no electrical resistance, then measures power-production behavior in `1 m/s` steps while varying controller duty ratio to locate the maximum-power operating point. (source: sources/va22.md)
- It estimates turbine rotational speed from generator three-phase frequency and reports startup at `3.5 m/s` plus rated-condition output of `114.7 W` at `9 m/s` and `170 rpm`. (source: sources/va22.md)

![Source figure](../../images/va8-fig5.jpg)
Original caption: Figure 5: Relation between lift coefficient and angle of attack. [[va8|Source]]
![Source figure](../../images/va9-fig27.jpg)
Original caption: Fig. 27. Different field tests scenarios. [[va9|Source]]
![Source figure](../../images/va9-fig28.jpg)
Original caption: Fig. 28. Field test sensors. [[va9|Source]]
![Source figure](../../images/va11-fig7.jpg)
Original caption: Fig. 7. VAWT prototype in wind tunnel [53]. [[va11|Source]]
![Source figure](../../images/va12-fig1.jpg)
Original caption: Figure 1. (a) Side-view and (b) top view of the wind tunnel test section with the two turbine array shown. In both views. the filled black rectangles represent the fan grid and the dashed black rectangles represent the maximum extent of the particle tracking measurement domain. The red dots illustrate the configuration of the seven-camera setup above the wind tunnel. All cameras were installed at the same height above the tunnel, and were oriented such that the turbine pair was in the center of the frame. (c) Illustration of the two turbine array geometry and the coordinate system used in the wind tunnel. Turbine 1 (T1) was defined as the upstream turbine and is located at a fixed position at (X, Y, Z) = (0, 0, 0). Turbine 2 (T2) is the downstream turbine and could be located at angles (phi) with respect to the freestream (U) within -90 degrees <= phi <= 90 degrees and turbine spacings (s) within 1.25 D <= s <= 3 D. Both turbines could be oriented to rotate either clockwise or counter-clockwise. [[va12|Source]]
![Source figure](../../images/va15-fig3.jpg)
Original caption: FIGURE 3 The three-bladed H-Darrieus wind turbine in the Durham 2 m2, 3/4 open-jet, open-return wind tunnel [[va15|Source]]
![Source figure](../../images/va22-fig7.jpg)
Original caption: Figure 7. Wind tunnel test section. [[va22|Source]]

Limitations:
- Scaling mismatch with real-world conditions. (source: sources/HRI2526.md)
- Limited ability to estimate full power output. (source: sources/HRI2526.md)

Related:
- [[Wind Turbine Parameters]]
- [[Urban Wind Conditions]]
- [[CFD]]
- [[PIV Testing]]
- [[3D Particle Tracking Velocimetry]]
- [[VAWT Aerodynamic Design Parameters|Aerodynamic Design Parameters]]
- [[Double-Multiple Streamtube Model]]
- [[va15 Blade Surface Roughness]]
- [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]]

#methods
