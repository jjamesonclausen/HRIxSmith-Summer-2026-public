---
Title: "ANALYSIS AND OPTIMIZATION OF A SAVONIUS-DARRIEUS HYBRID WIND TURBINE"
Author: "Edmond Maican, Liliana Dumitrescu, Radu Radoi, Oleg Ciobanu, Dragos Preda"
Published: 2020
Created: ""
Processed: true
tags:
- "sources"
---

#sources
# ANALYSIS AND OPTIMIZATION OF A SAVONIUS-DARRIEUS HYBRID WIND TURBINE

Edmond Maican, Liliana Dumitrescu, Radu Radoi, Oleg Ciobanu, Dragos Preda

INOE 2000 - Subsidiary Hydraulics & Pneumatics Research Institute, Romania

S.C. Rolix Impex Series S.R.L., Romania

## Abstract

Savonius and Darrieus rotors are the most popular vertical axis wind turbines (VAWT). However, both of them have disadvantages: low starting torque of the Darrieus rotor, which prevents it from self-starting, and low speed of the Savonius rotor which makes it inappropriate for power generation. Using a hybrid Savonius-Darrieus turbine is a solution to compensate these disadvantages. In this paper the torque of a Darrieus-Savonius hybrid wind turbine is estimated by means of computational fluid analysis (CFD), and improved designs are proposed and analysed, in order to establish the increase in performance against the original model. A first change in design was to remove the shaft from the inside of the Savonius rotor. A second change consists in the removal of the Savonius rotor from inside of the Darrieus one and placing it outside the rotor. CFD analysis was performed on these configurations. For the first one, the torque increased by 10.5%, while the average torque increase for the second configuration reached 22.3%.

## Keywords

Wind turbine, Savonius, Darrieus, CFD, Optimization, Torque, Renewable energy

## 1. Introduction

The increasing concern on climate change, as well as actual goals for clean and renewable energy deployment, have triggered during the last decades a rapid development of green energy technologies. In order to be competitive on the energy market, the cost of green energy should be further reduced by means of improved equipment designs.

Large scale wind farms already proved to be suitable, wind being one of the most abundant pollution free energy sources. Small wind turbines are also developed for local use, but research is still under development for better and cheaper designs and efficiency. Using CFD software is of great help in estimating and improving new designs in a more realistic way than ever. It is an accurate and cost-effective alternative to lab scale testing and provides means to perform quick changes on simulation conditions, as well as to rapidly assess modified designs.

Savonius is a drag-based, simple, vertical axis equipment (Figure 1), but it is also characterized by a relatively low performance. As an advantage, it is self-starting at low wind speeds due to its high torque. This "S"-shaped rotor was developed by S.J. Savonius and, according to his research, the maximum efficiency of his prototype was 37% (Savonius, S.J., 1931; Gupta, R., Das, R., Sharma, K.K., 2006). Many attempts have been made to optimize its geometry, by experimental means and/or using mostly 2D CFD analysis.

The lift-based Darrieus rotors (Figure 2) have usually two or three blades with a symmetric, thin, NACA cross-section. They are aerodynamic efficient, with power coefficient Cp approx. 0.4, thus being comparable with horizontal axis wind turbines (HAWT) (Hashem, I., Mohamed, M.H., 2018; Tjiu, W., Marnoto, T., Mat, S., et al., 2015; Pallotta, A., Pietrogiacomi, D., Romano, G.P., 2020). These rotors are characterized by high-power output, but they have a low starting torque which renders them unable to self-start unless certain accidental wind conditions are met. Their performance is negatively affected by the windstream turbulence (Fujisawa, N., Shibuya, S., 2001; Kyozuka, Y., 2008).

![Figure 1: Basic design of a Savonius rotor](vj2-fig1.jpg)

![Figure 2: (a) The "TEV 100" Darrieus generator, made by ICPITMUA Brasov; nominal power: 100 kW; nominal wind speed: 11...13 m/s; blade profile: NACA 0015; maximum Cp: 0.38. (b) The "TEV 20" H-type Darrieus generator, made by ICPITMUA Brasov; nominal power: 20 kW; blade profile: NACA 0012; nominal wind speed: 11 m/s; maximum Cp: 0.31](vj2-fig2a.jpg)
![Figure 2: (a) The "TEV 100" Darrieus generator, made by ICPITMUA Brasov; nominal power: 100 kW; nominal wind speed: 11...13 m/s; blade profile: NACA 0015; maximum Cp: 0.38. (b) The "TEV 20" H-type Darrieus generator, made by ICPITMUA Brasov; nominal power: 20 kW; blade profile: NACA 0012; nominal wind speed: 11 m/s; maximum Cp: 0.31](vj2-fig2b.jpg)

An approach to overcome both the Savonius lack of efficiency for power generation and the Darrieus poor starting torque, is to place both rotors on the same shaft in a hybrid wind turbine configuration. Thus, the Savonius rotor can be used to start the Darrieus one in low wind speeds.

Several studies have been made in this direction. M. Abid et al. placed a Savonius rotor at the top of a Darrieus one. They noticed a significant improvement in turbine's operation at lower wind speeds (as low as 3 m/s). Their testing was carried out using a permanent magnetic generator sponsored by industry rated (Abid, M., Karimov, K., Wajid, H., et al., 2015). T. Letcher experimented on combined Savonius-Darrieus wind turbines and concluded that these hybrid rotors can operate at low wind speeds and perform better than HAWT (Letcher, T., 2010). S.M. Rassoulinejad-Mousavi et al. investigated the performance of a Savonius rotor that was combined with a H-type Darrieus rotor with a DUW200 blade profile. They placed the Savonius rotor at the middle of the Darrieus one (configuration 1), and at the bottom (configuration 2). Compared to Darrieus and Savonius rotors taken individually, the second configuration generated more power, while the first one showed a better coefficient of performance (Rassoulinejad-Mousavi, S., Jamil, M., Layeghi, M., 2013). A.S. Siddiqui et al. experimented on three hybrid configurations: (1) Savonius rotor was placed at the middle of the Darrieus one; (2) and (3) Savonius rotor placed at the top and, respectively, bottom of the Darrieus one. They concluded that the highest coefficient of performance was achieved in the first configuration, while configuration (3) had the lowest one (Siddiqui, A.S., Mian, S.N., Alam, M. et al., 2018).

## 2. Materials and Methods

A hybrid rotor with a helical Savonius rotor placed at the middle of a Darrieus rotor with three helical blades was designed and investigated (Figure 3). The purpose of this study is to maximize the torque developed for lower wind speeds, of 7 m/s. The Savonius rotor has a height of 1000 mm and a diameter of 500 mm. The Darrieus rotor has a diameter of 1600 mm, and the length of the NACA 0018 blade projected on a vertical plane (blade height) is 1800 mm. The NACA profile has a chord length of 110 mm. Both rotors are mounted on the same shaft, with a diameter of 38 mm in the area corresponding to the Savonius rotor. The overlapping space between the two Savonius blades (see Figure 1) is 58 mm, which means that the shaft occupies about 66% of this space.

During the first step of torque optimization, this first configuration of the hybrid wind turbine was analysed at different angles with respect to wind direction, using the SolidWorks Flow Simulation module. Due to the large time necessary for each simulation (more than 3 hours), only nine equally spaced angles of attack were considered, from 0 to 120 degrees.

To take into consideration the influence of the 3D vortex-like structures, the problem was solved in a 3D computational domain, as such complex phenomena cannot be modeled based on to a 2D geometry with some simple 3-D effects corrections. The computational domain boundaries were placed far enough from the regions close to the turbine where the solution accuracy is important. The computational domain is 15 m long, 12 m high, and 12 m wide. The origin of the CAD model (see Figure 3 b) is at 6 m from the inlet, 6.5 m from the top, and 6 m from the lateral side of the computational domain.

These dimensions were calculated based on data and research published on specific literature (Rezaeiha, A., Kalkman, I., Blocken, B., 2017; Marsh, P.; Ranmuthugala, D.; Penesis, I.; Thomas, G., 2015). Mesh refinement was performed on all model surfaces in order to preserve good results accuracy.

Nominal windspeed velocity was set to 7 m/s at the inlet of the domain, and standard atmospheric conditions are assumed (25 C, 101 kPa). For this kind of analysis, flow turbulence in the domain is expected to be medium turbulent and approximately isothermal. Therefore, a typical value of 5% turbulence intensity was assumed (Rumsey, C., 2020). Simulations consisted of measurements of the static torque generated when the hybrid rotor was locked at nine different angles every 15 degrees, taken between 0 and 120 degrees relative to flow direction.

SolidWorks Flow Simulation uses the Favre-averaged Navier-Stokes equations to predict turbulent flows. These equations use the time-averaged effects of the turbulence on the flow parameters, while the time-dependent, large-scale phenomena are directly considered. For turbulent kinetic energy Flow Simulation uses the Lam and Bremhorst modified k-e model, which describes turbulent, laminar, and transitional flows of homogeneous fluids (Sobachkin, A., Dumnov, G., 2014).

![Figure 3: (a) CAD model of the initial configuration of the proposed hybrid wind turbine (at the bottom - bearing housing and power generator); (b) simplified CAD model for CFD analysis](vj2-fig3a.jpg)
![Figure 3: (a) CAD model of the initial configuration of the proposed hybrid wind turbine (at the bottom - bearing housing and power generator); (b) simplified CAD model for CFD analysis](vj2-fig3b.jpg)

## 3. Results

The Flow Simulation solver uses a robust approach that allows relatively fast convergence with large timesteps. However, the resulting convergence behavior proved to be "bouncy" for about the first third of the simulation time and, for three simulations (30 degrees, 45 degrees, and 60 degrees) further mesh refinement was necessary until a smooth numerical stability was obtained. For all of them the number of iterations and calculation time were much longer than in the other cases.

Figure 4 shows the turbulent flow due to the Savonius component (side and top views). It is expected that these turbulences negatively affect proper operation of the Darrieus blades that are lift-based and require laminar flow.

![Figure 4: Turbulent flow due to the Savonius rotor for an angle of attack of 30 degrees: (a) - side view; (b) - top view](vj2-fig4a.jpg)
![Figure 4: Turbulent flow due to the Savonius rotor for an angle of attack of 30 degrees: (a) - side view; (b) - top view](vj2-fig4b.jpg)

Table 1 shows the torque generated by the hybrid wind turbine in this configuration, for each angle of attack.

| Angle (degrees) | 0 | 15 | 30 | 45 | 60 | 75 | 90 | 105 | 120 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Torque (Nm) | 1.174 | 1.390 | 1.683 | 1.611 | 1.486 | 1.498 | 1.347 | 1.122 | 1.075 |

A second potential negative influence on the calculated torque values could be the large diameter of the shaft, which has structural role but blocks the internal flow within the Savonius rotor, hindering the air circulation from one blade to another (Figure 5).

To study the influence of the shaft on torque performance of the hybrid wind turbine, the design was changed removing the shaft from the inside of the Savonius rotor, thus improving the air flow through the gap between the two blades. In this new configuration, bending and torsional stresses should however be taken over by the Savonius blades themselves.

Also, as the Savonius rotor generates important turbulence that affect the operation of the Darrieus blades, a second design configuration consisting in the removal of the Savonius rotor from inside of the Darrieus one was made. The Savonius rotor was split into two halves, each with no shaft, and each of them being positioned one at the top and the other at the bottom of the Darrieus rotor (Figure 6).

CFD analysis was then performed on these two new optimized configurations, using the same setups as in the case of the initial design. The purpose was to establish the increase in performance against the original model.

Figure 7 shows that the turbulence produced by the Savonius rotor has now influence on a much smaller portion of the Darrieus blades, towards their top and bottom sides.

Table 2 shows the torque values obtained for the original design as well as for each of the two optimized configurations. The last two columns show the increase in torque relative to the original design, for one third of a complete rotation, in steps of 15 degrees. While removing the shaft from the Savonius turbine produced an average increase in torque of 10.5%, the highest gain of 22.3% was obtained without shaft and with the Savonius rotor removed from within the Darrieus space and placed at the top and bottom of the turbine. However, this increase can also be partially explained by the increase in swept area. Figure 8 shows a graphical representation of torque variation for the original design and the two optimized configurations.

![Figure 5: The shaft (in blue) occupies about 66% of the overlapping space between the two blades of the Savonius rotor](vj2-fig5.jpg)

![Figure 6: The Savonius rotor was split in two halves that were placed on top and bottom of the hybrid wind turbine](vj2-fig6.jpg)

![Figure 7: The influence of turbulence produced on the Darrieus blades is reduced compared with the original design; (a) - side view; (b) - top view](vj2-fig7a.jpg)
![Figure 7: The influence of turbulence produced on the Darrieus blades is reduced compared with the original design; (a) - side view; (b) - top view](vj2-fig7b.jpg)

| Angle (degrees) | Original configuration Torque Torig (Nm) | Configuration 1 Torque T1 (Nm) | Configuration 2 Torque T2 (Nm) | T1 - Torig (Nm) | T1 - Torig (%) | T2 - Torig (Nm) | T2 - Torig (%) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 1.174 | 1.403 | 1.583 | 0.229 | 19.51 | 0.409 | 34.84 |
| 15 | 1.39 | 1.605 | 1.688 | 0.215 | 15.47 | 0.298 | 21.44 |
| 30 | 1.683 | 1.835 | 1.7 | 0.152 | 9.03 | 0.017 | 1.01 |
| 45 | 1.611 | 1.665 | 1.913 | 0.054 | 3.35 | 0.302 | 18.75 |
| 60 | 1.486 | 1.654 | 1.827 | 0.168 | 11.31 | 0.341 | 22.95 |
| 75 | 1.498 | 1.619 | 1.673 | 0.121 | 8.08 | 0.175 | 11.68 |
| 90 | 1.347 | 1.434 | 1.565 | 0.087 | 6.46 | 0.218 | 16.18 |
| 105 | 1.122 | 1.231 | 1.516 | 0.109 | 9.71 | 0.394 | 35.12 |
| 120 | 1.075 | 1.200 | 1.493 | 0.125 | 11.63 | 0.418 | 38.88 |
| Average torque increase (%) |  |  |  | 10.5 |  | 22.32 |  |

![Figure 8: Torque values calculated for each configuration, for one third of a complete rotation (15 degree steps)](vj2-fig8.jpg)

## 4. Conclusions

The CFD analysis of the three different designs of the hybrid Darrieus-Savonius wind turbine confirmed that both the shaft removal from inside the Savonius rotor, and placing the Savonius rotor outside the Darrieus one, improve the torque significantly. Removing the shaft from the original design added 10.5% to the torque over one third of a complete revolution, for a 7 m/s wind speed. Placing two no-shaft halves of the Savonius rotor at the top and bottom of the hybrid wind turbine further increased the torque by 11.8% when compared to the first configuration, and to a total of 22.3% when compared to the original design.

To conclude, these results can be further improved by performing additional studies to optimize the influence of the overlapping space between the two blades of the Savonius rotor for the average wind speed in the area of interest.

## Acknowledgement

This work was carried out under the project CONVENER - Creating a high-level competence core in the field of increasing the conversion efficiency of renewable energies and energy autonomy through the combined use of resources [RO: Crearea unui nucleu de competenta de inalt nivel in domeniul cresterii randamentului de conversie a energiilor regenerabile si a autonomiei energetice prin utilizarea combinata a resurselor], Grant no 37/02.09.2016, funded by the European Regional Development Fund through the Competitiveness Operational Programme 2014-2020.

## Note

This paper is based on the paper presented at ISB-INMA TEH 2020 International Symposium (Agricultural and Mechanical Engineering), organized by Politehnica University of Bucharest - Faculty of Biotechnical Systems Engineering (ISB), National Institute of Research-Development for Machines and Installations Designed to Agriculture and Food Industry (INMA Bucharest), Romanian Agricultural Mechanical Engineers Society (SIMAR), National Research and Development Institute for Food Bioresources (IBA Bucharest), National Institute for Research and Development in Environmental Protection (INCDPM), Research-Development Institute for Plant Protection (ICDPP), Research and Development Institute for Processing and Marketing of the Horticultural Products (HORTING), Hydraulics and Pneumatics Research Institute (INOE 2000 IHP) and "Food for Life Technological Platform", in Bucharest, Romania, 30 October, 2020.

## References

1. Abid M., Karimov K., Wajid H., Farooq F., Ahmed H., Khan O., (2015), Design, Development and Testing of a Combined Savonius and Darrieus Vertical Axis Wind Turbine, Iranica Journal of Energy and Environment, 6(1), 1-4.
2. Fujisawa N., Shibuya S., (2001), Observations of dynamic stall on Darrieus wind turbine blades. Journal of Wind Engineering & Industrial Aerodynamics, 89, 201-2014.
3. Gupta R., Das R., Sharma K., (2006), Experimental study of a Savonius-Darrieus wind machine. Proceedings of the International Conference on Renewable energy for Developing Countries.
4. Hashem I., Mohamed M., (2018), Aerodynamic performance enhancements of H-rotor Darrieus wind turbine. Energy, 142, 531-545.
5. Kyozuka Y., (2008), An experimental study on the Darrieus-Savonius turbine for the tidal current power generation. Journal of Fluid Science and Technology, 3(3), 439-449.
6. Letcher T., (2010), Small scale wind turbines optimized for low wind speeds. 24th Hayes Graduate Research Forum. http://hdl.handle.net/1811/45531.
7. Marsh P., Ranmuthugala D., Penesis I., Thomas G., (2015), Three-dimensional numerical simulations of straight-bladed vertical axis tidal turbines investigating power output, torque ripple and mounting forces. Renewable Energy, 83, 67-77.
8. Pallotta A., Pietrogiacomi D., Roman G., (2020), HYBRI - A combined Savonius-Darrieus wind turbine: Performances and flow fields. Energy, 191, 116433.
9. Rassoulinejad-Mousavi S., Jamil M., Layeghi M., (2013), Experimental study of a combined three bucket H-rotor with Savonius wind turbine. World Applied Sciences Journal, 28(2), 205-211.
10. Rezaeiha A., Kalkman I., Blocken B., (2017), CFD simulation of a vertical axis wind turbine operating at a moderate tip speed ratio: Guidelines for minimum domain size and azimuthal increment. Renewable Energy, 107, 373-385.
11. Rumsey C., (2020), Turbulence Modeling Resource. From: Langley Research Center: https://turbmodels.larc.nasa.gov/index.html.
12. Savonius S. J., (1931), The S-rotor and its application. Mechanical Engineering, 53(5), 333-338.
13. Siddiqui A., Alam M., Memon A., Mian S., Haq M., Jamil M., (2018), Experimental Study to Assess the Performance of Combined Savonius Darrieus Vertical Axis Wind Turbine at Different Arrangements. 2018 IEEE 21st International Multi-Topic Conference (INMIC), 18356007.
14. Sobachkin A., Dumnov G., (2014), Numerical Basis of CAD-Embedded CFD. From: DS SolidWorks: https://www.solidworks.com/sw/docs/Flow_Basis_of_CAD_Embedded_CFD_Whitepaper.pdf.
15. Tjiu W., Marnoto T., Mat S., Ruslan M., Sopian K., (2015), Darrieus vertical axis wind turbine for power generation I: assessment of Darrieus VAWT configurations. Renewable Energy, 75, 50-6.
