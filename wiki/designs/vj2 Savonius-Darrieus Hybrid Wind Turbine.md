---
Created: 2026-07-03
Source: [[vj2]]
Tags: "#designs"
Cp:
Efficiency:
TSR:
Swept area:
Cut-in speed:
Starting torque:
Rated speed:
Rated power:
---

## Savonius-Darrieus Hybrid Wind Turbine

The source presents a hybrid VAWT that places a helical Savonius rotor together with a three-bladed helical Darrieus rotor to improve startup torque while retaining Darrieus lift-based performance. (source: sources/vj2.md)

## Geometry

- The base design uses a helical Savonius rotor placed at the middle of a three-bladed helical Darrieus rotor. (source: sources/vj2.md)
- Savonius height: 1000 mm. (source: sources/vj2.md)
- Savonius diameter: 500 mm. (source: sources/vj2.md)
- Darrieus diameter: 1600 mm. (source: sources/vj2.md)
- Darrieus blade projected height: 1800 mm. (source: sources/vj2.md)
- Darrieus blade profile: NACA 0018. (source: sources/vj2.md)
- Darrieus blade chord length: 110 mm. (source: sources/vj2.md)
- The shared shaft diameter is 38 mm through the Savonius region. (source: sources/vj2.md)
- The overlap space between the Savonius blades is 58 mm. (source: sources/vj2.md)

![Figure 3: initial hybrid CAD model.](../../images/vj2-fig3a.jpg)
![Figure 3: simplified CAD model for CFD analysis.](../../images/vj2-fig3b.jpg)

## Unique Design Choices

- The study focuses on a hybrid arrangement where the Savonius rotor provides drag-based starting torque and the Darrieus rotor provides lift-based output. (source: sources/vj2.md)
- The source identifies the internal Savonius shaft as a possible flow obstruction because it occupies about 66% of the overlap space. (source: sources/vj2.md)
- One optimized configuration removes the shaft from inside the Savonius rotor. (source: sources/vj2.md)
- A second optimized configuration splits the Savonius rotor into two no-shaft halves and places them at the top and bottom of the Darrieus rotor. (source: sources/vj2.md)

![Figure 5: shaft blocking the Savonius overlap space.](../../images/vj2-fig5.jpg)
![Figure 6: split Savonius placement at top and bottom.](../../images/vj2-fig6.jpg)

## Performance

- The CFD study evaluates static torque at 7 m/s across nine attack angles from 0 degrees to 120 degrees. (source: sources/vj2.md)
- The original configuration reports torque values from 1.075 Nm to 1.683 Nm across the tested angles. (source: sources/vj2.md)
- Removing the shaft from the Savonius rotor reports an average torque increase of 10.5% relative to the original design. (source: sources/vj2.md)
- Splitting the Savonius rotor into two no-shaft halves and moving them outside the Darrieus space reports a 22.3% average torque increase relative to the original design. (source: sources/vj2.md)
- The source says the second configuration also improves torque by 11.8% relative to the first optimized configuration. (source: sources/vj2.md)
- The source notes that some of the second configuration's improvement may be partly explained by increased swept area. (source: sources/vj2.md)

![Figure 7: reduced turbulence influence on Darrieus blades, side view.](../../images/vj2-fig7a.jpg)
![Figure 7: reduced turbulence influence on Darrieus blades, top view.](../../images/vj2-fig7b.jpg)
![Figure 8: torque values for the three configurations.](../../images/vj2-fig8.jpg)

## Related

- [[Hybrid VAWT]]
- [[Savonius Turbine]]
- [[Darrieus Turbine]]
- [[vj2 Savonius Shaft Removal]]
- [[vj2 Savonius Placement Outside Darrieus Rotor]]

#designs
