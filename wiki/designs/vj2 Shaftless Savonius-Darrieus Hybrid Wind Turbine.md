---
Created: 2026-07-03
Source: [[vj2]]
Tags: #designs
max Cp (1-4 m/s): 
max Cp (4-8 m/s): 
Efficiency (%): 
max TSR (1-4 m/s): 
max TSR (4-8 m/s): 
Swept area (m^2): 2.88
Cut-in speed (m/s): 
Cut-out speed (m/s): 
max starting torque (Nm), (0-3 m/s): 
Rated speed (m/s): 
Rated power (W): 
---
## Shaftless Savonius-Darrieus Hybrid Wind Turbine

This `vj2` configuration keeps the original three-bladed helical Darrieus rotor and central helical Savonius layout, but removes the shaft from inside the Savonius rotor to reduce internal flow blockage. (source: sources/vj2.md)

## Geometry

- The Darrieus rotor remains a three-bladed helical rotor with NACA 0018 blades. (source: sources/vj2.md)
- The Savonius rotor remains at the middle of the Darrieus rotor. (source: sources/vj2.md)
- The design change is the removal of the 38 mm shaft from the Savonius overlap region. (source: sources/vj2.md)
- In the original configuration, that shaft occupied about 66% of the 58 mm overlap space between the Savonius blades. (source: sources/vj2.md)

![Source figure](vj2-fig5.jpg)
Original caption: Figure 5: The shaft (in blue) occupies about 66% of the overlapping space between the two blades of the Savonius rotor [[vj2|Source]]

## Unique Design Choices

- The source treats the internal shaft as a flow obstruction that hinders circulation from one Savonius blade to the other. (source: sources/vj2.md)
- Removing the shaft shifts bending and torsional load carrying toward the Savonius blades themselves. (source: sources/vj2.md)

## Performance

- The CFD study evaluates static torque at 7 m/s across nine attack angles from 0 degrees to 120 degrees. (source: sources/vj2.md)
- Removing the shaft reports an average torque increase of 10.5% relative to the original configuration. (source: sources/vj2.md)
- The source reports positive torque gains at every tested angle, ranging from 3.35% to 19.51%. (source: sources/vj2.md)

![Source figure](vj2-fig8.jpg)
Original caption: Figure 8: Torque values calculated for each configuration, for one third of a complete rotation (15 degree steps) [[vj2|Source]]

## Related

- [[vj2 Savonius-Darrieus Hybrid Wind Turbine]]
- [[vj2 Split Savonius Outside Darrieus Hybrid Wind Turbine]]
- [[vj2 Savonius Shaft Removal]]
- [[Hybrid VAWT]]

#designs
