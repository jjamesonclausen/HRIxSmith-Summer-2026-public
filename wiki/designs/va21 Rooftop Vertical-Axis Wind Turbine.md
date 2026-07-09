---
Created: 2026-07-06
Source: "[[va21]]"
tags:
  - designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
max Cp (8-12 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
max TSR (8-12 m/s): 
Swept area (m^2): 
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## Rooftop Vertical-Axis Wind Turbine

The `va21` paper presents a small experimental rooftop VAWT that was built and installed on an urban building in Kolkata for combined performance testing and CFD comparison. (source: sources/va21.md)

## Geometry

- The assembly uses `4` blades mounted around a `510 mm` diameter rotating disc. (source: sources/va21.md)
- The rotor support table is reported as `865 mm x 250 mm x 10 mm`, with a flanged rotating tube of `70 mm` outer diameter and `120 mm` flange diameter. (source: sources/va21.md)
- The turbine is mounted at the south-west corner of the roof on a `0.45 m` thick parapet wall, with a brick support pillar of plan area `1.2 m x 0.6 m`. (source: sources/va21.md)
- The blades are straight, tapered, and twisted by a trial-and-error process intended to improve torque production under low urban wind conditions. (source: sources/va21.md)

![Source figure](va21-fig3.jpg)
Original caption: Figure 3. Major components of the WT: (a) isometric view and (b) photographic view. Legends: 1. Blades (04 in count); 2. Holding table; 3. Vertical axis of rotation; 4. Table legs (04 in count); 5. Threaded stud (04 in number); 6. Electrical motor (DC to AC); 7. Large spur gear; 8. Hollow flanged attachment (source: Shantanu Dutta). [[va21|Source]]
![Source figure](va21-fig5.jpg)
Original caption: Figure 5. WT and motor details (source: Authors' elaboration). [[va21|Source]]

## Unique Design Choices

- The generator shaft is directly aligned with the turbine shaft to reduce mechanical losses instead of using an intermediate speed-up stage in the current prototype. (source: sources/va21.md)
- The paper explicitly leaves slots and adjustable supports in the assembly so future versions can add a chain-sprocket or belt-pulley system for higher shaft speed. (source: sources/va21.md)
- The electrical system couples the rotor to a permanent magnet generator, `12 V` battery, UPS inverter, display units, and a change-over switch for DC and AC handling. (source: sources/va21.md)

## Performance

- In rooftop wind measurements, the rotor speed increased from `75 rpm` to `100 rpm` as wind magnitude rose across the reported component ranges `0.4-3.8 m/s` in `vx` and `0.5-3.8 m/s` in `vy`. (source: sources/va21.md)
- In controlled electrical-output tests, shaft speeds from `55 rpm` to `115 rpm` produced `3-11.9 V`, `20-130 mA`, and `0.05-2.7 W`. (source: sources/va21.md)
- The source reports nonlinear vibration growth with shaft speed, with measured displacement up to `46 mm`, vibration velocity up to `399 mm/s`, and acceleration up to `29 m/s^2` depending on direction and measurement point. (source: sources/va21.md)
- The CFD comparison reports less than `10%` deviation in rotor speed and less than `20%` deviation in voltage and power versus measured data, while also noting that the simplified blade geometry and `2D` model likely contribute to the remaining error. (source: sources/va21.md)

> Discrepancy: The source estimates a `7-15 year` payback even though it also reports only `0.05-2.7 W` measured output and describes the prototype as supplementary rather than a full home-power replacement. That is more optimistic than other low-wind rooftop cases currently summarized in [[Economic Viability of VAWTs]]. (source: sources/va21.md, sources/HRI2526.md)

## Related

- [[Architectural Wind Turbines]]
- [[Urban Wind Conditions]]
- [[CFD]]
- [[Economic Viability of VAWTs]]

#designs
