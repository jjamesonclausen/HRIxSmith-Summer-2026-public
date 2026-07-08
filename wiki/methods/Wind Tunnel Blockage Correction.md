---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[va23]], [[vj26]]
Source_count: 2
Tags: #methods
---
## Wind Tunnel Blockage Correction

Method for correcting VAWT power coefficient and tip-speed-ratio measurements when the wind tunnel test section is small enough that the turbine materially accelerates the surrounding flow. (source: sources/va23.md)

- The `va23` paper starts from Pope and Harper's low-speed wind-tunnel blockage approach for unusually shaped objects, then modifies it for rotating VAWTs. (source: sources/va23.md)
- In that study, blockage ratio is defined as turbine swept area divided by wind-tunnel test-section area, and the raw blockage ratio is about `19.1%`, well above the level where the paper says correction is normally required. (source: sources/va23.md)
- The method corrects both `Cp` and `lambda` by first estimating a correction factor `epsilon_t`, then using that to compute corrected velocity `Uc`. (source: sources/va23.md)
- Unlike a pure area-ratio correction, the paper also measures local side-flow velocity `Uside` with a hot-wire probe and uses the ratio `U/Uside` to refine the blockage estimate for each turbine and operating condition. (source: sources/va23.md)
- The source says the correction lowers `Cp`, shifts the `Cp-lambda` curves leftward, and better represents blockage effects created by turbine rotation and geometry. (source: sources/va23.md)
- The vj26 review adds a higher-level warning that blockage can greatly affect Savonius wind-tunnel testing, especially for high-solidity rotors, so blockage handling is not optional for trustworthy interpretation. (source: sources/vj26.md)

![Source figure](va23-fig6.jpg)
Original caption: Figure 6. A schematic of the velocity measurement locations at the ABL wind tunnel: A, hot-wire anemometer experimental setup. B, Top view of the rotor inserted into the ABL wind tunnel, where U and Uside are velocities, AT, As are areas for the tunnel and the turbine. C, Front view schematic of the velocity measurement locations for the three different configurations (dimensions are not to scale). [[va23|Source]]

Related:
- [[Wind Tunnel Testing]]
- [[CFD and Validation]]
- [[Blade-Wake Interaction]]

#methods
