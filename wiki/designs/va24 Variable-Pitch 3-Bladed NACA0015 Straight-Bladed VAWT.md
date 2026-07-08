---
Created: 2026-07-06
Source: [[va24]]
Tags: #designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
Swept area (m^2): 
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## Variable-Pitch 3-Bladed NACA0015 Straight-Bladed VAWT

The `va24` paper studies a straight-bladed Darrieus rotor under active variable-pitch control, comparing fixed blades with two pitch-control strategies integrated into a DMST model. (source: sources/va24.md)

## Geometry

- The results section repeatedly describes the studied rotor as a `3`-bladed NACA0015 configuration. (source: sources/va24.md)
- The paper says the blade-pitching techniques are evaluated on a straight-bladed NACA0015 rotor and discusses instantaneous response for TSR values `4`, `5`, and `6`. (source: sources/va24.md)

> Discrepancy: The source results repeatedly refer to a `3`-bladed rotor, but the validation table included in the same paper lists a `2`-bladed reference turbine with `R = 3 m`, `h = 6 m`, and `c = 0.2 m` for model validation. The paper does not cleanly separate those two parameter sets. (source: sources/va24.md)

![Source figure](va24-fig9.jpg)
Original caption: Fig. 9. Comparison of Cp against different TSR from 2 to 9 for fixed blades compared against active blade pitching model techniques 1 and 2. [[va24|Source]]
![Source figure](va24-fig11.jpg)
Original caption: Fig. 11. Instantaneous Coefficient of Performance (Cp) as a function of one blade azimuth position obtained using Variable blade pitching technique 1 and 2 compared to fixed 3 blade rotor configuration at TSR 4 (a, b), 5(c, d), and 6 (e, f). [[va24|Source]]

## Unique Design Choices

- Technique 1 uses a sinusoidal blade-pitch function to vary local angle of attack cyclically during rotation. (source: sources/va24.md)
- Technique 2 broadens the angle-of-attack profile into a more linear form so the blade remains close to the optimum pre-stall angle through more of the cycle. (source: sources/va24.md)
- The source frames both methods as active control strategies that keep the local angle of attack below stall in both upstream and downstream rotor regions. (source: sources/va24.md)

## Performance

- The fixed-blade case reaches a peak `Cp` of about `0.48` at `TSR = 5`. (source: sources/va24.md)
- Technique 1 raises that peak to `Cp = 0.568` at `TSR = 5` with `S = 8.5 degrees`, while Technique 2 reaches `Cp = 0.532` at `TSR = 5` with `S = 6 degrees`. (source: sources/va24.md)
- At `TSR = 7`, the paper reports `Cp = 0.53` for Technique 2 at `S = 4 degrees`, compared with about `0.35` for the fixed-blade case and `0.49` for Technique 1 at `S = 5 degrees`. (source: sources/va24.md)
- At `TSR = 2`, both pitch techniques improve the modeled dead-band behavior from near-zero `Cp` to about `0.1`. (source: sources/va24.md)

## Related

- [[Straight-bladed Darrieus]]
- [[Double-Multiple Streamtube Model]]
- [[va24 Variable Blade Pitching Strategy]]

#designs
