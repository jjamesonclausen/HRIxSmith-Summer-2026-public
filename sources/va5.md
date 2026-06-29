#sources
# Design and Construction of Vertical Axis Wind Turbine

Piyush Gulve and Dr. S. B. Barve

## Abstract
The project aims at rural electrification via a hybrid wind-solar system. The authors design a compact vertical-axis wind turbine (VAWT) suitable for rooftops and small domestic loads. They choose a VAWT over a HAWT because it is compact, quieter, easier to install and maintain, and can accept wind from all directions.

## 1. Introduction
Wind turbines convert wind energy into electricity. A vertical axis wind turbine has a shaft normal to the ground. The paper divides VAWTs into drag and lift types, and argues that the vertical arrangement simplifies design and allows the generator and drivetrain to be mounted at ground level.

The paper also notes that VAWTs are not self-starting and usually have lower tip-speed ratio than HAWTs.

## 2. Literature Survey

### 2.1 Theoretical Maximum Efficiency
Wind power is expressed as:

```math
KE = \frac{1}{2}\rho A V^3
```

The paper states that wind turbines cannot exceed the Betz limit, with maximum `Cp = 0.593`.

### 2.2 Practical Efficiency
Practical losses include:

- tip losses
- wake effects
- drive train efficiency losses
- blade shape simplification losses

### Comparison of Different Wind Turbines
The paper compares rotor types and uses this comparison to justify a drag-type VAWT for a low-cost design.

## 3. Design Calculations
The design targets 35 W of output. Assuming 25% turbine efficiency and 85% generator efficiency, the paper estimates a required wind power of 166 W.

Using wind velocity 6.67 m/s and air density 1.225 kg/m^3, the swept area is calculated as 1 m^2, with rotor diameter 1 m and rotor height 1 m.

Blade sizing is then estimated as:

- wing width = diameter x 0.14 = 0.140 m
- wing chord = circumference x 0.09 = 0.282 m

## 4. CAD Design
The paper shows CAD views of the wooden frame, the blades, the exploded view, and the assembly.

### Figures
Figure 1: configurations for shaft and rotor orientation.
![Figure 1: configurations for shaft and rotor orientation](../images/va5-fig1.jpg)

Figure 3: blade parameters.
![Figure 3: blade parameters](../images/va5-fig2.jpg)

Figure 4: block diagram.
![Figure 4: block diagram](../images/va5-fig3.jpg)

Figure 5-8: CAD design, assembly, turbine specifications, and observation table.
![Figure 5-8: CAD design, assembly, turbine specifications, and observation table](../images/va5-fig4.jpg)

> Note: additional extracted crops are saved as `images/va5-fig5.jpg` through `images/va5-fig11.jpg`.

## 5. Design Specifications

| Item | Value |
| --- | --- |
| Rated power | 35 W |
| Cut-in speed | 3 m/s |
| Rated speed | 6.67 m/s |
| Rotor diameter | 1 m |
| Swept area | 1 m^2 |
| Gear box | None |
| Brake | Not required |
| Generator type | DC generator |
| Blade type | J-type (drag) |
| Blade number | 3 |
| Blade material | GI sheet with wooden frame |
| Blade length | 1 m |
| Cup radius | 0.126 m |

## 6. Results Discussion
The prototype efficiency is reported as 23.3%, slightly below the planned 25% because of manufacturing errors and friction losses.

## 7. Conclusion
The authors conclude that VAWT-based systems are practical for low-cost renewable electrification, especially in rural or rooftop settings.

## 8. Future Scope
The paper recommends more precise fabrication, more aerodynamic blade design, CFD-based refinement, and improved alternators/dynamos.

## References
1. Schubel and Crossley, wind turbine blade design.
2. Denson, reliability prediction history.
3. Gipe, Wind Power.
4. Castillo, Small-scale Vertical Axis Wind Turbine Design.
5. windgenkits.com.
6. windstuffnow.com.
7. Vishnuvardhan and Prasad, FEA and experimental investigations on small wind turbine blades.
8. Sajid, Reddy, and Nagesh, design of VAWT for optimum power.
9. Kohli and Ahuja, performance prediction in HAWT.
