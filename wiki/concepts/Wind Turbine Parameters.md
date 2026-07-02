---
Created:
Updated: 2026-07-02
Sources:
- [[sources/HRI2526.md]]
- [[sources/va4.md]]
- [[sources/va5.md]]
- [[sources/va6.md]]
- [[sources/va7.md]]
- [[sources/vj1.md]]
- [[sources/vj10.md]]
- [[sources/vj11.md]]
- [[sources/vj12.md]]
- [[sources/vj6.md]]
Source_count: 10
Tags:
- concepts
---
## Wind Turbine Parameters

Key metrics used to evaluate wind turbine performance. (source: sources/HRI2526.md)

- Cut-in speed: wind speed at which the turbine begins rotating (source: sources/HRI2526.md)
- Cut-out speed: wind speed at which the turbine shuts down to prevent damage (source: sources/HRI2526.md)
- Rated power: maximum power output of the turbine (source: sources/HRI2526.md)
- Rated speed: wind speed at which rated power is achieved (source: sources/HRI2526.md)
- Tip Speed Ratio (TSR): ratio of blade tip speed to wind speed (source: sources/HRI2526.md)
- Coefficient of Power (CP): ratio of extracted power to available wind power (source: sources/HRI2526.md)
- Starting torque: torque before rotation begins; must exceed system friction to self-start (source: sources/HRI2526.md)
- Swept area: area covered by turbine blades, typically height × diameter for VAWTs (source: sources/HRI2526.md)
- Reynolds number: indicates flow regime (laminar vs turbulent) (source: sources/HRI2526.md)

- The vj12 review treats aspect ratio, overlap ratio, multi-staging, blade count, blade profile, inner blades, end plates, twist angle, TSR, and Reynolds number as the main knobs for VAWT performance tuning. (source: sources/vj12.md)
- It says Savonius overlap has no universal optimum, but 0.1-0.15 is often useful and some studies still favor no-overlap for higher mechanical power. (source: sources/vj12.md)
- It notes that Reynolds-number increases generally improve Cp and static torque in Savonius studies. (source: sources/vj12.md)

- Betz limit: theoretical maximum power coefficient (~0.59). (source: sources/vj1.md)
- Solidity: ratio of blade area to swept area; influences performance and structural tradeoffs. (source: sources/vj1.md)
- The CFD review repeatedly uses power coefficient, torque, flow separation, and wake dynamics as the main performance indicators for VAWT studies. (source: sources/vj6.md)
- The helical VAWT case found peak power coefficient near TSR 1.8 and used power fluctuation as a stability metric. (source: sources/va4.md)
- The rooftop J-type design in va5 targets 35 W output, 3 m/s cut-in speed, and 6.67 m/s rated speed. (source: sources/va5.md)
- The comparison paper reports peak efficiencies of 50% for a three-blade HAWT and 40% for a Darrieus VAWT, with tip-speed ratios of 14.3 and 5.1 respectively. (source: sources/va6.md)
- It also reports power coefficients around 0.5 for HAWTs and 0.4 for VAWTs. (source: sources/va6.md)
- In the wind-shear HAWT study, vertical wind shear reduces angle of attack and lift coefficient, reduces power coefficient, and increases thrust coefficient. (source: sources/vj10.md)
- The same study reports that most wind-shear-driven coefficient changes occur between 0.2 and 0.8 of blade length, with little effect near the root region. (source: sources/vj10.md)
- In the helical-VAWT helix-angle study, the coefficient of performance is treated as the product of TSR and average moment coefficient. (source: sources/va7.md)
- The study uses the standard deviation of Cp as a cyclic-loading smoothness metric; higher helix angles reduced this standard deviation, while the 60-degree helical blade gave the highest reported power performance. (source: sources/va7.md)

The VAWT review gives typical design ranges of TSR 0.6-1.2 for Savonius and 2.5-5.0 for Darrieus, with peak Cp around 0.15-0.25 and 0.35-0.45 respectively. (source: sources/vj11.md)
It treats solidity, blade profile, pitch angle, blade count, and chord Reynolds number as the main geometry-performance knobs. (source: sources/vj11.md)
It says startup, torque ripple, and wake interaction are the practical metrics that sit alongside Cp when comparing designs. (source: sources/vj11.md)

## Figures

![Figure 6: power coefficient versus TSR at Re = 60,800](../../images/va4-fig6.jpg)
![Figure 6: power versus wind speed](../../images/va6-fig6.jpg)
![Figure 4: peak efficiencies](../../images/va6-fig4.jpg)
![Figure 5-8: CAD design, assembly, turbine specifications, and observation table](../../images/va5-fig4.jpg)
![Figure 8: Distribution of angle of attack](../../images/vj10-fig8.jpg)
![Figure 10: Distribution of thrust coefficient](../../images/vj10-fig10.jpg)
![Figure 7: coefficient of performance across helix angles](../../images/va7-fig7.jpg)
![Figure 14: standard deviation of Cp across blade types and TSR](../../images/va7-fig14.jpg)

These parameters are often visualized using a power curve, which relates wind speed to power output. (source: sources/HRI2526.md)

Related:
- [[VAWT]]
- [[Darrieus Turbine]]
- [[Savonius Turbine]]
- [[Wind Shear]]

#concepts 
