===== PAGE 1 =====
ELSEVIER
Journal of Cleaner Production 435 (2024) 140475
Contents lists available at ScienceDirect
Journal of Cleaner Production
journal homepage: www.elsevier.com/locate/jclepro
Cleaner
Prod tion
Check for
updates
Parameter optimization method of contra-rotating vertical axis wind
turbine: Based on numerical simulation and response surface
Peng Zheng a, Hexiang Zhang a, Zutao Zhang ' , Waleed Salman a, Mansour Abdelrahman
a
a School of Mechanical Engineering, Southwest Jiaotong University, Chengdu 610031, PR China
b
Chengdu Technological University, Chengdu 611730, PR China
ARTICLE INFO
Handling Editor: Jin-Kuk Kim
Keywords:
Contra-rotating vertical axis wind turbine
(CRVAWT)
Computational fluid mechanics (CFD)
Improved delayed detached eddy simulation
(IDDES)
Response surface
Parameter optimization
1. Introduction
ABSTRACT
In recent years, the depletion of oil resources and increased in air pollution have become the two most serious
challenges in the world. Therefore, the offshore vertical axis wind turbine (VAWT) has become a subject of
increasing scholarly interest. However, the instability problem of VAWT has become an important reason that
limits its continued development. Contra-rotating vertical axis wind turbines (CRVAWT) can improve the re-
covery efficiency of wind energy and improve the stability of wind turbines. However, the research on simulation
analysis and parameter optimization of CRVAWT is not perfect, and further research is needed. This study first
performed a numerical simulation of an isolated VAWT using STAR CCM + simulation software and compared
the simulation results with wind tunnel tests to verify the accuracy of the model. After that, simulated and
comparatively analyzed the proposed CRVAWT. The results indicated that the CRVAWT exhibits a lower power
coefficient but better stability than the isolated VAWT. Then, simulations and analyses were conducted on the
pitch angle, relative airfoil thickness, rotor spacing, and included angle of the CRVAWT. Finally, a four-
parameter, three-level response surface optimization scheme was established using Design-Expert to optimize
the blade parameters and obtain the optimal configuration of the contra-rotating wind turbine parameters. After
optimization, the power coefficient (Cp) of the CRVAWT is 0.1837, which is 36.68% more than the Cp of pre-
optimization and reaches 99.19% of the Cp of the isolated VAWT. And the total torque of the turbine is
reduced by 96.96%, which provides a significant stability advantage.
In recent years, the depletion of oil resources and increased air
pollution have become two of the most critical challenges globally.
Therefore, to meet the energy needs of all areas of a country, it is highly
recommended that renewable, sustainable energy sources or technolo-
gies have low C02 emissions. In addition, according to the 2022 Global
Carbon Budget Report (GCBR), global carbon emissions reached 40.5
billion tons in 2022, an increase of 1% compared to 2021 (Global-
carbonproject.org). Hence, the environmental pollution caused by fossil
fuels seriously affects the ecosystem and human existence (Jahangiri
et al., 2022), (Marx et al., 2019). Therefore, renewable and sustainable
energy sources, such as wind energy, solar energy, wave energy, kinetic
energy conversion, etc., are receiving more attention (Sadorsky, 2021a)
Al-Shahri, 2021), (Hoang et al., 2022). Furthermore, wind energy
generation has been studied for a long time, is now more maturely
developed, and occupies an important position in the renewable energy
* Corresponding author.
E-mail address: zzt@swjtu.edu.cn (Z. Zhang).
https://doi.org/10.1016/j.jclepro.2023.140475
industry (
Sadorsky, 2021 b), (Masdari et al., 2019). Moreover, according
to the 2022 National Electricity Industry Statistics Published (NEIB) by
the National Energy Administration of China (NEAC), China's installed
wind power capacity reached about 370 million kilowatts by the end of
2022, an increase of 11.2% per year (). On the other hand, offshore wind
power has become an important direction for filture wind power
development due to its abundant wind energy resources, convenient
transportation and installation, and easy site selection of wind farms
Wu et al., 2019), (Diaz and Soares, 2020)
The wind energy generation based on the turbines can be divided
into wind energy generation with horizontal axis turbines and wind
energy generation with vertical axis turbines (Kumar et al., 2018), Pope
et al., 2010
). Horizontal axis wind turbines (HAWTs) have the advan-
tages of low self-starting wind speed, wide coverage, and high power
factor (
Kumar et al., 2019), (Bai and Wang, 2016) and have been
developed vigorously in the past decade. Subsequently, VAWTs have
unique advantages, including (i) low manufacturing, installation, and
Received 13 August 2023; Received in revised form 18 November 2023; Accepted 27 December 2023
Available online 30 December 2023
0959-6526/0 2023 Elsevier Ltd. All rights reserved.
===== PAGE 2 =====
P. Zheng et al.
CiteSpace
vertical axis wind turbin&lade
axis wind turbine
angle
powey performance
domain size
ppprovement
turbulence models
aerodynamic performance
dy mics
computationa ui ynamics
de Ign
wind ener
Odel
flow
computational fluid dynamic (cf
models
rf
am c stall
irfoil
opti ation
simulation
aerodynamics
number
power coefficien
airfoils
solidity
Journal of Cleaner Production 435 (2024) 140475
#0 vertical axis wind turbine
#1 gurney flap
#2 computational fluid dynamics
#3 finite element analysis
#4 wind energy
#5 design optimization
#6 design of the experiment
#7 blade structure
#8 submerged generator
Fig. 1. Research hotspots of wind turbines in recent years.

![Figure 1](../images/vj8-fig1.jpg)
maintenance costs, (ii) less noise generation, (iii) uniform force on the
turbine as a whole, and (iv) a simple system that can run smoothly in any
wind direction without the need for a yaw system. Moreover, based on
the working principle of VAWTs, they can be divided into drag-type
wind turbines, such as Savonitls type, and lift-type wind turbines, st1Ch
as Darrieus type (Islam et al., 2013), (Kouloumpis et al., 2020
). Firstly,
the Savonius type wind turbine drives the rotation of the wind turbine
by the pressure difference between the concave and convex surfaces of
the blade, making it suitable for low wind speed areas such as cities due
to its small starting wind speed and low cost (Al-Kayiem, 2016), (Cue-
vas-Carvajal et al., 2022). Secondly, the Darrieus type wind turbine re-
lies on the lift force provided by the airfoil to drive rotation, with a
simple structure, high efficiency of wind energy utilization, insensitivity
to wind direction, and great advantages in multi-directional high wind
speed application scenarios such as offshore wind energy recovery (
Tjiu
et al., 2015a), (Mohamed, 2012
). However, VAWTs also face challenges,
such as low wind energy utilization and poor self-start performance
(Bhutta et al., 2012), Tjiu et al., 2015b)
In addition, one of the important factors that restrict the further
development of VAWT is the instability catlsed by tlneven stress on the
offshore platform. Therefore, improving the stability and aerodynamic
performance of VAWTs are urgent problems to be solved, and investi-
gating a new type of VAWT is necessary. For further analysis to explore
the literature gaps, the bibliometric analysis was performed in CiteSpace
software to plot the entire literature on wind turbines in recent years, as
shown in Fig. 1
However, from Fig. 1, it can be seen that research on
VAWTs has been a hot issue in recent years. Furthermore, research on
contra-rotating VAWTs and parameter optimization of VAWTs is still
relatively limited.
Moreover, it can be inferred from the bibliometric study's findings
that many scholars are researching ways to improve the aerodynamic
performance of VAWT.
su et al. (2020)
proposed a VAWT using V-sha-
ped blades and used the k-(D turbulence model for simulation analysis.
Their results showed that V-shaped blades could reduce the impact of
lateral loads on VAWT and effectively restrain the blades, dynamic stall
phenomenon, the power coefficient can be increased by about 24.1%. In
another study, Wong et al. (2018) suggested a flat deflector analyzed
using ANSYS Fluent Simulation Software to find the influence of pa-
rameters such as the position, inclination angle, and length of the
deflector on VAWT. Their results show that the deflector can increase
the average torque coefficient by 47.1%. In addition,
Didane et al.
(2018a)
designed a new type of co-axial contra-rotating VAWT, put the
S-type rotor inside the H-type rotor, and used CFD software to simulate
and analyze the model. Their system results demonstrated that the new
model improves the start-up of VAWT capacity for an additional three
times the power across the entire wind speed range. Moreover, the au-
thors in (
Stl et al., 2020
) created a variable pitch VAWT and carried out
experiments in a wind tunnel and simulated different wind turbine pa-
rameters using the LES turbulence model.
Currently, there are two main methods for research on vertical axis
wind turbines: experimental testing method and computational fluid
dynamics simulation method. Firstly, regarding experimental testing
methods, Vergaerde et al. (2020) studied paired vertical axis wind tur-
bines and compared three combinations of isolated, side-by-side, and
reverse rotation through wind tunnel tests and deeply studied the effect
of wake on VAWT. Their finding showed that the paired VAWTs have
excellent performance compared with HAWTs. Additionally,
Li et al.
(2021)
analyzed the robustness of dual vertical axis wind turbines and
simulated the urban environment through a wind tunnel and conducted
experiments on dual vertical axis wind turbines and isolated vertical axis
wind turbines. Their results showed that the impact of dual VAWT on
power output was small. However,
Eboibi et al. (2016) studied the in-
fluence of consistency on the performance of VAWT through experi-
ments and used particle image velocimetry to measure the flow field
around VAWT at different concentrations. Their results showed that
VAWT with low consistency would start to stall earlier. In another study,
through wind tunnel tests,
Peng et al. (2019)
evaluated the power
generation of VAWT with different length-to-diameter ratios. According
to their experiment findings, the power coefficient of the wind turbine
increased by about 100% in turbulent flow than in advective flow and
was proportional to the length-to-diameter ratio of the wind turbine.
Meanwhile, it is proportional to and inversely proportional to length.
Li
et al. (2016) conducted detailed tests on VAWT in a wind tunnel and
field experiments, respectively, and analyzed the influence of pitch
angle, Reynolds number, and wind speed on the fan power, and their
experimental data has high research value.
Secondly, regarding computational fluid dynamics, The authors in
Zhang et al., 2020) conducted a simulation analysis on the blade
thickness, camber, and span shape of VAWT. They optimized the airfoil
parameters through the Latin hypercube sampling method, and their
2
===== PAGE 3 =====
P. Zheng et al.
Recover wind energy I
with VAWT
Mesh of model
Model of
VAWT
0.2
0.0
1-02
0.2
Counter-rotating Vertical
Axis Wind Turbi e
0.4 0.6 0.8
1.0
—NACAOOIS —NACA0018
—NACA0021 —NACA0024
0) Blade airfoil
@ Included angle
of rotor
Accuracy
verification
Independence
verification
Model of
CRVAWT
Blade Airfoil
Pitch Angle
1)
O Rotor spacing
@ Pitch angle
Rotor Spacing
Included Angle
VAWT Analysis
Parameter Analysis
CRVAWT Analysis
Journal of Cleaner Production 435 (2024) 140475
Response surface
Enhanced Stability
and Efficiency
Establish response
surface model
Parameter
Optimization
Response surface
Fig. 2. Schematic diagram of CRVAWT simulation analysis and optimization.

![Figure 2](../images/vj8-fig2.jpg)
analysis showed that the symmetrical airfoil straight blade best per-
formed. Moreover, Hilewit et al. (2019) conducted a simulation analysis
of STS-VAWT with three different parameters and developed an aero-
dynamic code that combines blade element theory (BET) and vortex
filament method (VFM) to predict the power of VAWT. Their finding
demonstrated that 50% STS-VAWT peak power can be increased by
about 14%. In another study,
Day et al. (2021)
applied the adjoint
method to the optimization of VAWT and simulated and optimized the
model through ANSYS Fluent software, and the optimized blade power
coefficient has been improved to a certain extent. Naccache et al.
Naccache and Paraschivoiu, 2018) conducted parametric research and
simulations on the dual vertical axis wind turbine (D-VAWT), consid-
ering the wind angle, number of blades, and airfoil profile of D-VAWT.
Their simulation results showed that D-VAWT can operate efficiently in
different ranges of tip speed ratios. Additionally, Rezaeiha et al. (2018)
simtllated VAWT tinder different tip speed ratios and consistencies, and
they analyzed several important parameters in the simulation guidelines
for azimuthal increment, domain size, and convergence, which have a
high value for CFD simulation research. Nevertheless, Ivo et al. (Mar
inic-Kragic et al., 2020) optimized the design of Savonius blades using
2D CFD and compared it with the design using 3D CFD, and their results
showed that the maximum power factor of the newly designed turbine
was increased by 9%.
Nevertheless, the contra-rotating vertical axis wind turbine has
overall stability advantages and is particularly suitable for collecting
wind energy on offshore floating platforms. It can effectively solve the
problems of poor stability and low wind energy utilization of VAWT.
Poguluri et al. (2021) carried out an aerodynamic study for a co-axial
contra-rotating vertical axis wind turbine (CR-VAWT). The wind speed,
wake velocity profile, and fixed blade pitch angle of the CR-VAWT were
analyzed, and their results showed that the power of the contra-rotating
VAWT is lower at high wind speeds but with negligible aerodynamic
torque and side-side force. The authors in. (
Lee et al., 2022
) developed
an analytical tool for contra-rotating VAWTs using AeroDyn to evaluate
the loads and motions of contra-rotating VAWTs. Their results showed
that the aerodynamic power of the reverse rotating VAWT is reduced,
but its fatigue loads are lower than those of the conventional VAWT. In
addition, Djamal et al. (Didane
al., 2018b
) proposed a novel
contra-rotating vertical axis wind turbine by combining Savonius-type
and Darrieus-type VAWTs with a contra-rotating design to obtain a
higher relative speed. Their simulation results showed that their new
system can reduce the starting torque and increase the aerodynamic
torque and power by a factor of three.
Although many scholars have conducted a series of experimental and
simulation studies on various VAWTs, relatively few design and simu-
lation studies have been conducted on CRVAWTs, and no specific pa-
rameters have been studied and optimized. Therefore, the purpose of
this study is to investigate the dimensional parameters of CRVAWTs
through simulation and parameter optimization and to obtain the
optimal design parameters for further research and structural design of
CRVAWTs. This study used the CFD analysis software STAR CCM + to
establish a CRVAWT model, and three different turbulence models
(Realizable k- e, SST k- (D, and IDDES) are compared and analyzed. In
addition, four CRVAWT parameters (the pitch angle /3 of the blade, the
relative thickness of blade airfoil TR, the spacing d between the rotors,
and the included angle 0) are simulated and analyzed. Finally, a
response surface design scheme with four factors and three levels is
determined through response surface analysis, and the optimized
calculation is obtained to identify the parameters of the optimal
CRVAWT.
The main content of this paper is organized as follows:
Section 2
describes the model and mesh of isolated wind turbines, verifies the
feasibility of the model, and analyzes the independence of the mesh.
Section 3
introduces the model and CFD simtllation details of the
contra-rotating wind turbine and conducts simulation analysis on the
four parameters of the wind turbine. Section 4 analyzes the simulation
results of CRVAWT and optimizes the dimensional parameters by
response surfaces based on Section 3. Finally, conclusions are presented
In Section 5.
2. Methodology
This study utilizes the finite volume-based CFD software STAR CCM
+ for simulation calculations and conducted STAR CCM+ a general CFD
3
===== PAGE 4 =====
P. Zheng et al.
Upper
rotor
Disk
generator
Lower
rotor
(a) Structure of CRVAWT
Blade
support
Floating
platform
Journal of Cleaner Production 435 (2024) 140475
c
(b) Parameter dimension of CRVAWT
Fig. 3. Model and parameters of CRVAWT.

![Figure 3](../images/vj8-fig3.jpg)
Table I
Dimensional parameters of CRVAWT.
Parameters
Radius of blade
Height of blade
Spacing between rotors
chord length
pitch angle
Unit
Value
1000
1200
300
265
6
analysis software based on finite elements, known for its accuracy and
speed in processing complex geometries and achieving fast solutions.
Furthermore, it also offers features such as model generation, meshing,
and post-processing. However, to ensure the validity and accuracy of the
simulations, it is crucial to compare the simulation data with wind
tunnel experimental data and analyze the mesh model independently.
provides a schematic diagram of the research design for this paper.
Fig. 2
2.1. Model design
The proposed study performs simulation calculations and parametric
analysis for Darrieus-type contra-rotating wind turbines. In addition, the
Wall
Inlet
Rotation domain
simulation results are compared with the wind tunnel experimental data
of the wind turbine model by
Li et al. (2016)
to verify the feasibility of
the simulation model. The CRVAWT was modeled in this study using the
parametric CAD modeling program SolidWorks 2019, as shown in
a. The vertical axis wind turbine consists of an upper rotor and a
Fig. 3
lower rotor, with each rotor containing two NACA0021 blades con-
nected by brackets. The two rotors rotate in opposite directions, with a
disk generator attached between them and a floating platform at the
bottom of the turbine. The radius R and height H of the rotor are 1000
mm and 1200 mm, respectively, while the chord length c of the blades is
265 mm. The spacing d between the rotors is set to 0.25 H, and the blade
pitch angle /3 is set to 60 based on Li's experimental data.
Table 1
and
b respectively show the values and labels of specific parameters for
Fig. 3
reference.
2.2. Computational domain and mesh
Before simulating the CRVAWT, an isolated VAWT simulation model
should be established and analyzed in comparison with the experimental
data to verify the accuracy of the simulation model. However, the
simulation model consists of a computational domain that includes both
the fluid and rotational domains. The fluid domain is designed to be
rotation track
tlet
Fan
c
Ø3 2R
IOH
Fluid domain
5011
IOH
(a) Schematic diagram of the calculation computational field (b) Top view of the rotation field
Fig. 4. Calculation domain of VAWT.

![Figure 4](../images/vj8-fig4.jpg)
4
===== PAGE 5 =====
P. Zheng et al.
(a) Mesh of rotational domain
(b) Mesh of blade
(c) of boundary layer
Journal of Cleaner Production 435 (2024) 140475
very well. Especially for turbulence in large-scale structures, it can
effectively solve turbulence problems close to the wall. Becatlse the
airflow near the blade surface is very intense, a very dense meshing is
required to capture the pressure and velocity distributions. Therefore, a
fine prismatic boundary layer mesh needs to be generated on the blade
surface. The basic size of the blade surface is set to 7.5 mm, with the
minimum size set to 2.5 mm.
The wall ftlnctiony is a dimensionless number that determines the
size of the boundary layer region cells (Song et al., 2015), (Balduzzi
et al., 2016
). The calculation formula of the wall function y is shown
below.
Fig. 5. Topology diagram of the numerical mesh.

![Figure 5](../images/vj8-fig5.jpg)
Expenment
IDDES
SST 1<-0
Realizable k-c
Re pul/g
q 0.058Re 02
0.5Cff)UN
p/UTP
(1)
0.22
0.18
0 0.14
0.10
0.06
I .25
1.50
1.75
2.00
2.25
2.50
TSR
Fig. 6. Torque of three turbulence models at different TSRs.

![Figure 6](../images/vj8-fig6.jpg)
large enough to avoid any influence from the boundary on the simula-
tion results. The wall surface of the fluid domain is set as a slip wall
surface. The incoming airflow direction is perpendicular to the axial
direction of the fan, with an inlet velocity of 8 m/s. The rotational
domain is a cylinder that is slightly larger than the rotation range of the
blade. An interface is created in the simulation environment to enable
data transfer between the fluid and rotational domains.
shows the
specific dimensions of the computational domain.
In the fluid domain, the airflow moves from the inlet to the outlet,
with the main flow direction. The generation speed of cut volume grids
is fast, which can reduce time costs and is suitable for grid partitioning in
domains with main flow directions. Therefore, the trimmer cell mesh
was selected for the mesh generation of the fluid domain to achieve
higher calculation efficiency, while given the lower calculation accuracy
required for the fluid domain, the base size is set to 500 mm, and the
minimum size is set to 125 mm. Moreover, the mesh at the contact
surface between the two domains is refined, and the cell size is set to 50
mm to ensure a smooth transition of the cell size between the fluid and
the rotating domains.
However, the airflow in the rotating domain is more complex and
requires higher calculation accuracy for vortex or rotation. Polyhedral
meshes have good computational convergence and can automatically
identify and encrypt areas with complex flow states. Therefore, the
polyhedral mesh is selected for the mesh generation of the rotating
domain. The calculation accuracy of the rotation domain is high, and the
base size is set to 50 mm, with the minimum size set to 25 mm.
Since IDDES uses the LES model to simulate the boundary layer, it
can capttlre the details and structures in the ttlrbulent boundary layer
where p is the fluid density, u is flow characteristic velocity, I is char-
acteristic size, is dynamic viscosity, Re is Reynolds number, Cf is wall
friction coefficient, is wall shear stress, [Joo is flow velocity, UT is the
fluid velocity on the blade surface, and y is the height of the first mesh
layer on the blade stlrface.
The value y plays an important role in the accuracy of boundary
layer simulations. If y + is too large, the first grid point falls outside the
logarithmic layer, and if it is too small, the first grid point falls into the
viscous bottom layer of the boundary layer (
ANSYS and lnc, 2014
). The
inlet flow velocity for this study is 8 m/s, and based on the design size of
the blade, the calculated Reynolds number range is Re 1.62 x 105
2.89 x 105. To ensurey+ < 1 (
Elsakka et al., 2019), the thickness of the
first cell layer of the boundary layer is set to 0.0186 mm, and the total
thickness of the boundary layer is set to 10 mm. This study aims to
achieve accurate and reliable simulation results by carefully selecting
these parameters. The mesh generation details are shown in
for
Fig. 5
reference.
2.3. Validation study
The Realizable k- e Model (
) and SST k- (1)
SCHUMANN, 1977
) are commonly used turbulence models. The Realizable
MENTER, 1994
k- e Model was proposed by Schumann in 1977 and is an improvement
over the standard k- e model, with improved calculation equations for
vortex flow and separated flow. It is more suitable for turbulence
simulation of rotating bodies. On the other hand, the SST k- (D Model was
proposed by Menter in 1994 and is an improvement over both the k- e
and k- (D models. It combines the advantages of the two models and has a
good treatment for the energy attenuation effect in the flow field.
In addition, this study also selected the improved Delayed Detached
Eddy Simulation (IDDES) model proposed by Shtlr et al. (2008)
in 2008.
The Detached Eddy Simulation (DES) (Spalart, 1997) is a hybrid model
that combines Large Eddy Simulation (LES) and Reynolds-Averaged
Navier-Stokes (RANS). This model applies different calculation
methods in different fluid regions, which can effectively solve the wall
turbulence problem. The resolution reqtlirement of DES mesh is not as
strict as that of LES, which greatly reduces the computing cost. The
IDDES model is an improvement over DES, which can effectively solve
the turbulence problem near the wall.
The Tip Speed Ratio (TSR) is an important parameter for wind tur-
bines. It is used to define the ratio of the linear speed of the tip of the
wind rotor blade to the wind speed and can be expressed as:
(2)
where (D is the angular velocity of the rotor, R is the radius of the rotor,
5
===== PAGE 6 =====
P. Zheng et al.
Table 2
Mesh dependency test based on the relative errors of the power coefficient.
Mesh
type
Mesh
1
Mesh
2
Mesh
3
Total
number
of cells
1.2e6
2.7e6
5.5e6
Simulation
Computing
time
14 h
30 h
65 h
value of Cp
0.19172
0.18836
0.18793
Experiment
value of Cp
0.18518
Relative
errors
3.41%
1.69%
1.46%
and V is the wind speed. The power coefficient (Cp) is an important
parameter used to evaluate the power generation efficiency of wind
turbines. It reflects the wind energy capture ability of wind turbines,
which can be expressed as:
(3)
P AV3 ¯ pHRV3
The turbulence model strongly influences the simulation, so it is
important to find the most accurate turbulence model. Keeping the other
simulation parameters consistent, the simulations were carried out for
each of the three turbulence models at different tip speed ratios.
Fig. 6
shows the comparison between the power coefficients and the experi-
mental values in the three turbulence models.
The simulation results obtained from the three turbulence models
were quite different. At low TSR, the simulated and experimental values
were relatively close to each other.
The maximum power coefficients for the IDDES, Realizable k-e and
SST k-(D turbulence models were achieved at TSR 2.22. The gaps be-
tween the peak power coefficients obtained from the simulations and the
experimental values were 1.69%, 3.11%, and 7.23%, respectively.
Among the three ttlrbulence models, the IDDES model had a power
coefficient peak value that was more consistent with the experimental
value. Therefore, the IDDES turbulence model was considered to be
more accurate for simulating VAWT.
2.4. Mesh independence analysis
The size of the cell has a great influence on the accuracy of the
simulation calculation results. The finer the cell size, the more accurate
the simulation results, but it will consume a lot of hardware resources
and time. Hence, a balance needs to be struck between accuracy and
computational cost.
However, to ensure the correct simulation of the boundary layer
velocity, pressure, and stability of the simulation results, three mesh
types are designed, including 1.2e6, 2.7e6, and 5.5e6 units, and the
simulation calculations are performed separately under the maximum
Journal of Cleaner Production 435 (2024) 140475
power coefficient.. The turbulence model Select IDDES. The Mesh de-
pendency test based on the relative errors of the power coefficient is
shown in
Table 2.
Based on the test results, it was found that mesh 1 had the fastest
simulation speed, but there was a significant difference between the
results and the experimental value, reaching 3.41%. The error between
the results and the experimental value of Mesh 3 was the smallest, only
1.46%. However, the number of cells was the largest, and the running
time was the longest. The simulation process of mesh 2 required only
half the running time of mesh 3, and the error was only 1.69%. There-
fore, the mesh generation method of mesh 2 was chosen for further
research, achieving a balance between hardware resources, time cost,
and accuracy.
3. Simulation details
3.1. CRVAWTmode1
To investigate the aerodynamic performance of the contra-rotating
vertical axis wind turbine and the influence of different parameters, a
CRVAWT model was established based on the research conducted in the
second chapter. The CRVAWT comprises two identical VAWTs with an
upper rotor and a lower rotor. The two rotors are co-axial with identical
parameters, and the upper rotor rotates counterclockwise while the
lower rotor rotates clockwise.
The calculation domain of the CRVAWT consists of a fluid domain
and a rotation domain. The parameters of the fluid domain are the same
20
10
O
-10
-20
0.65
Fig. 8.

![Figure 8](../images/vj8-fig8.jpg)
—Upper of CRVAWT
VAWT
Lower rotor of CRV AWT
CRVAWT
0.85
1.05
1.25
1.45
1.65
Wall
Time (s)
Torque comparison between VAWT and CRVAWT.
Outlet
doßai0
Upper rotor
0.25H
Lower rotor
Inlet
1.6R
1 OH
gotatioo
doloain
SOH
Fig. 7. Computational domain of CRVAWT.

![Figure 7](../images/vj8-fig7.jpg)
6
===== PAGE 7 =====
P. Zheng et al.
ß
fan
Rotation
path
Blade
chord
x
0.2
0.1
0.0
-0.1
-0.2
0.0
Fig. 9. Schematic diagram of the blade pitch angle.

![Figure 9](../images/vj8-fig9.jpg)
NACA0015
NACA0018
— NACA0021
NACA0024
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
Fig. IO. Cross sections of four airfoils.

![Figure 10](../images/vj8-fig10.jpg)
as those used in the second chapter. The spacing between the upper and
lower rotors is set as the chord length of the blades, and the angle dif-
ference between the two rotation domains is set to 00. The size param-
eters of the calculation domain are shown in
. The mesh generation
Fig. 7
parameters are consistent with the mesh parameters used in Section 2.
However, due to the inclusion of two rotors, the number of meshes in the
CRVAWT model exceeds 4 million, and the simulation time is approxi-
mately 50 h.
To verify the aerodynamic performance of the CRVAWT, the torques
of CRVAWT and the VAWT were compared and analyzed under the same
experimental conditions of inflow velocity V 8 m/s.
Upper rotor
Rotation
domain
Lower rotor
Journal of Cleaner Production 435 (2024) 140475
shows the torque comparison of CRVAWT and VAWT. The
Fig. 8
torque trend of the rotors of the two wind turbines is similar, but the
maximum torque of a single rotor of CRVAWT is 17.96 N m, while the
maximum torque of VAWT is 20.03 Nm, resulting in a difference of
11.68%. This difference is due to the opposite rotation direction of the
upper and lower rotors of CRVAWT, resulting in strong interaction at the
blade tips. The tip loss effect of the blades also reduces the torque
generated by the rotor (Poguluri et al., 2021), (Lee et al., 2022
). Under
the same experimental conditions, the torque generated by VAWT is
higher, indicating a higher utilization efficiency of wind energy.
Based on calculations, the wind power generation efficiency of a
single rotor of CRVAWT is 0.1344, while the wind power generation
efficiency of VAWT is 0.1852, resulting in a difference of approximately
27.4%.
Although the wind energy utilization efficiency of CRVAWT is
slightly lower compared to VAWT, CRVAWT has a significant advantage
in overall torque. In terms of the total torque of the wind turbine, the
torques of the upper and lower rotors of CRVAWT cancel each other out
due to their opposite rotation directions, resulting in a smaller total
torque transmitted to the support. The total peak torque of CRVAWT is
only0.636 N m, which is 3.04% of the peak torque of VAWT, providing a
more stable overall fan. Due to its excellent stability, CRVAWT is well-
suited for offshore floating platforms.
3.2. Parameter selection
Various parameters significantly impact the wind energy recovery
efficiency of a wind turbine. In this study, four parameters, including the
pitch angle /3 of the blade, the relative thickness of airfoil TR, the rotor
spacing d, and the included angle 0, were selected to analyze the
important parameters and find the best configuration.
The pitch angle /3 is the angle between the chord line of the blade
airfoil and the rotation plane of the wind turbine, and it has a significant
effect on changing the torque of the wind turbine. It is a key parameter
affecting the aerodynamic performance of the wind turbine, as shown in
Fig. 9, where a represents the angle of attack of the blade.
The NACA series airfoil has a higher maximum lift and lower drag
coefficients. In the previous study, the NACA0021 airfoil model was
used, where 00 indicates a symmetrical airfoil, and 21 indicates that its
relative thickness is 21 %. Other airfoils of this series include NACAOOI 5,
NACA0018, and NACA0024. This study conducted simtllation analyses
on these four airfoils to explore the influence of airfoil relative thickness
on the power coefficient of the wind turbine. The cross-sectional views
of the four airfoils are shown in
Fig. 10
Rotor
Rotation
\direction
Blade I
chord/
Rotation domain
(a) Spacing between upper and lower rotors
(b) Angle between upper and lower rotors
Fig. 11. Schematic diagram of spacing and included angle between rotors.

![Figure 11](../images/vj8-fig11.jpg)
7
===== PAGE 8 =====
P. Zheng et al.
200
-200
-150
-600
-soo
0.0
0.17
0.16
0.15
0.14
0.13
0.12
Upper rotor
Lower rotor
Average
Pitch angle (0)
(a) Diagrams of Cp of rotors with pitch angle
60
150
Journal of Cleaner Production 435 (2024) 140475
60
0.2
0.4
0.6
10
-1200
00
-450
60
1.0
0.4
06
Wc
0.0
0.2
0.4
0.6
x/c
0.8
(b) Upper section of blade_upwind
(c) Middle section of blade_upwind (d) Lower section of blade_upwind
150
100
-100
0.0
02
0.4
0.6
0.8
1-0
0-2
0.4
0.6
1.0
02
1.0
1.0
0.4
x/c
0.8
(e) Upper section of blade downwind (f) Middle section of blade downwind (g) Lower section of blade downwind
Fig. 12. Simulation results and analysis of blade pitch angle.

![Figure 12](../images/vj8-fig12.jpg)
In the CRVAWT, the two rotors rotate in opposite directions on the
same axis. The positional relationship between the upper and lower
rotors can also significantly impact the power coefficient of the wind
turbine. Therefore, it is necessary to study the spacing d and the angle 0
between the two rotors, as shown in
a and b.
Fig. 11
3.3. Response surface optimization
Response surface is a method used to regress and fit complex real
surfaces through limited experiments, enabling the specific relationship
between parameters and optimization objectives to be obtained. It ex-
presses the implicit relationship with clear and specific expressions,
making it convenient for calculation. Response surface is an efficient
optimization design method suitable for dealing with the effect of
multiple variables on a structure.
Commonly used experimental design methods for response surface
models include Central Composite Design, Optimal Space-Filling Design,
and Box-Behnken. The Box-Behnken Design (BBD) includes three levels:
center point 0, low-level point —1, and high-level point +1. It can be
analyzed within the range of 3—7 variables without multiple continuous
experiments and is an efficient response surface design method. There-
fore, In this study, Design Experts software was used and BBD design
method was chosen to optimize the analysis of four parameters, deter-
mining the response surface design scheme with four factors and three
levels. It establishes sample points for the optimized parameters within
the parameter design range, with a total of 29 sets of simulation ex-
periments. The design of the sample points and the analysis of the results
are carried out in the fourth chapter.
===== PAGE 9 =====
P. Zheng et al.
Upper rotor
0.14 Lower rotor
Average
0.13
0.12
0.11
0.10
15
18
21
24
Relative thickness of airfoil (%)
Fig. 13. Diagrams of Cp of the upper and lower rotors under different airfoils.

![Figure 13](../images/vj8-fig13.jpg)
4. Results and discussion
This study aims to simulate the impact of different parameters on the
aerodynamic performance of a wind turbine and optimize the parame-
ters tlSing the response surface method. The simulation software used is
STAR CCM+, and the calculations are performed on a small server
equipped with two Intel(R) Xeon(R) Silver 4210 R CPUs and 64 GB
memory. It takes about 50 h to complete a single simulation operation.
4.1. Simulation results
To understand the effect of fixed blade pitch angle on the aero-
dynamic performance of the wind turbine, the current study conducted
simulations with pitch angles of —30, 00, and 60 while keeping the other
parameters the same. However, the simulation results are shown in
a. At a pitch angle of [3 00, the average power coefficients of the
Fig. 12
upper and lower rotors are 10.4% higher than those of the rotor with a
pitch angle of —30 and 17.5% higher than those of the rotor with a pitch
angle of 60.
To further investigate the effect of blade pitch angle on torque, this
study plotted the surface pressure distribution of the upper rotor blade
cross-section when the rotor torque reaches its peak. The cross-sections
were plotted at three locations in the upper, middle, and lower parts of
the upper rotor, at 0.01 m, 0.6 m, and 1.19 m from the top of the blade,
respectively. The upper rotor contains two blades, with the blade near
the inlet referred to as blade_upwind and the blade away from the inlet
referred to as blade downwind.
b—d shows the blade surface
Fig. 12
pressure distribution for blade upwind, while
e and g show the
Figs. 12
blade surface pressure distribution of blade downwind.
x/c represents the ratio of the distance of the measured
In
Fig. 12,
point on the blade from the tip of the blade to the chord length of the
blade.
shows that different pitch angles exhibit opposite differ-
Fig. 12
ences in the performance of blade_upwind and blade_downwind. Ac-
cording to published research (O'meara and Mueller, 1987), the greater
the pressure difference on the blade stlrface, the greater the rotor torque.
In the three cross-sections of blade upwind, the pressure difference on
the blade surface is the largest at [3
— —30, and it decreases with
increasing pitch angle. In the blade downwind, the pressure difference
on the blade surface is largest at /3 60, and it decreases with decreasing
pitch angle. Because the torque of the upper rotor is the sum of the
torque of the two blades, the overall rotor torque is larger atß = 00. In
addition, the pressure at the lower section of the blades is significantly
smaller than the other sections, which explains the loss of the upper and
lower rotors of the convection fan.
Journal of Cleaner Production 435 (2024) 140475
To analyze the airfoil aspect of the blade, this study selected four
airfoils, namely NACA0015, NACA0018, NACA0021, and NACA0024,
for simulation comparison analysis while keeping other simulation pa-
shows the relationship between the power
rameters consistent.
Fig. 13
coefficient of CRVAWT and the airfoil type.
The average power coefficients of the upper and lower rotors of the
four airfoils are 0.1181, 0.1362, 0.1344, and 0.1335, respectively. The
rotor power coefficient of the NACA0015 airfoil is the lowest. In
contrast, the power coefficients of NACA0018 and NACA0021 are very
close to each other, indicating that the optimal airfoil parameters may be
between these two airfoils. To further investigate the reasons for the
differences between the different airfoils, this study analyzed the four
airfoils and plotted the contours of the instantaneous pressure distri-
bution on their surfaces in
The pressure difference on the surface
Fig. 14.

![Figure 14](../images/vj8-fig14.jpg)
of the NACA0024 airfoil is much smaller, with a pressure close to 799 Pa,
while the pressure difference on the surface of the NACA0015 is the
largest, close to 1.2 kPa. The surface pressure difference between the
NACA0018 and NACA0021 airfoils is 1014 Pa and 890 Pa, respectively.
(a) to 14(d) show that the highest pressures of the four airfoils
Fig. 14
are very close to each other, all around 131 Pa, but the difference be-
tween the lowest pressures is larger. The location of the lowest pressure
on the blade surface is framed by the red box in
Although
Fig. 14.
NACA0015 has the largest pressure difference, the lowest pressure range
is very small, which may be the reason for the lower power factor of the
rotor using the NACA0015 airfoil. To test this conjecture, this study
selected the pressure distribution data of the intermediate sections of
NACA0024 and NACA0015 for analysis, and the blade surface pressure
comparison of the two airfoil types is shown in
e. The pressure
Fig. 14
distributions of both blades are very close when the pressure is positive.
At x/c close to 0, the peak pressure difference is greater for NACA0015,
but it only remains dominant in a very small area at the top of the blade.
The overall pressure difference of the blade is lower than that of
NACA0024, so the turbine using the NACA0015 airfoil does not perform
well in terms of lift.
The positional relationship between the upper and lower rotors can
significantly impact the aerodynamic performance of the overall contra-
rotating fan. This study investigated the spacing between the upper and
lower rotors. The rotor spacing was set to the rotor chord length of 265
mm. According to previous studies, when the upper and lower rotors are
too close, they will interact with each other, thus reducing the overall
wind energy utilization efficiency of the fan. Therefore, this study
analyzed four different rotor spacing cases: 265 mm, 500 mm, 750 mm,
and 1000 mm.
a shows the relationship between the power co-
Fig. 15

![Figure 15](../images/vj8-fig15.jpg)
efficient of CRVAWT and rotor spacing.
a shows that as the rotor spacing increases, the power coef-
Fig. 15
ficient of the CRVAWT gradually increases, approaching the power co-
efficient of the isolated VAWT. To further investigate the effect of rotor
spacing on the power coefficient, this study plots the comparison of the
wake structures at different rotor spacing by depicting the Q-criterion
(Q 100) and relative velocity, as shown in
Fig. 15b
The results in
b show that when the upper and lower rotor
Fig. 15
spacing of the CRVAWT is small, the wake structures of the rotors are
very close and overlap each other. Due to the opposite speeds of the
upper and lower rotors, a strong interaction occurs as the blades
approach. The wake will absorb each other and spread out, and the
strongly interacting airflow will further affect the wind field around the
blades, reducing the pressure difference on the blade surfaces, thus
reducing the rotor speed and torque. In the case of a large distance be-
tween the upper and lower rotors, the wake structures of the rotors are
farther away and produce less mutual interference. Therefore, as the
distance between the rotors increases, the surface pressure difference of
the blades gradually increases, and the power coefficient of the rotor of
the CRVAWT will gradually approach that of the isolated VAWT.
However, an excessively long rotor spacing increases the center of
gravity of the wind turbine, making the turbine unstable. Therefore, the
length of the rotor spacing needs to be limited in response surface
9
===== PAGE 10 =====
P. Zheng et al.
—1054 6
Journal of Cleaner Production 435 (2024) 140475
—Sl 7.32
Pressure (Pa)
-5so.01
-342.69
-105.3S
131.94
—SS2.,S
-679.S3
Pressure (Pa'
-'77.05
.'31.29
(a) Two blades of the upper rotor of NACAOOI 5
(b) Two blades of the upper rotor of NACAOOI 8
-758.36
-sso.45
Pressure (Pa)
-402.53
-224.62
-46.712
131.20
-667. 19
-507.3S
Pressure (PO
-347.57
-1S7.75
-27.939
(c) Two blades of the upper rotor of NACA0021
300
-300
-600
-900
-1200
(d) Two blades of the upper rotor of NACA0024
A 15
NACA0024
0.0
A
0.2
AAA
00
0.4
0.6
0.8
1.0
x/c
(e) Pressure distribution in the middle section of NACA0015 and NACA0021
Fig. 14. Upper rotor surface pressures of four types of airfoils.
optimization.
In addition, the initial angle between the rotors may affect the sta-
bility of CRVAWT. This study simulated the angle range every 300 from
00 to 1800 and selected a total of six different included angles while
keeping other parameters constant.
a shows the variation of the
Fig. 16

![Figure 16](../images/vj8-fig16.jpg)
torque of the upper rotor of the wind turbine with different included
angles over time.
b shows the relationship between the total
Fig. 16
torque of wind turbines with different included angles and the variation
over time.
The results show that the torque of the upper rotor is almost the same
for all six different included angles. However, there is a significant dif-
ference in the total torqtle. When the included angle 0 between the upper
and lower rotors is 00 , the total torque is close to 0, and its impact on the
stability of the platform can be almost ignored. The closer the included
angle is to 900, the larger the total torque. At 0 900, the peak total
torque even exceeds the peak torque of the upper rotor. Therefore, in
subsequent optimization analysis, an inclusion angle close to 00 is very
important in the selection of the optimal solution.
4.2. Response surface results
To find the best fan parameter configuration, this study takes the four
parameters of the blade pitch angle [3, the blade airfoil TR, the spacing
d between the rotors, and the included angle 0 as the design variables. As
the spacing d between the rotors increases, the power of the CRVAWT
gradually approaches that of the VAWT. However, considering the
practical situation, if the spacing between the upper and lower rotors of
the CRVAWT is too long, it may result in a higher overall center of
gravity of the turbine, which can cause instability at high wind speeds.
Hence, the power coefficient and overall stability of the turbine need to
10
===== PAGE 11 =====
P. Zheng et al.
—0=900
0.18
0.16
0.14
0.12
Upper rotor
Lower rotor
Average
265
500
750
Journal of Cleaner Production 435 (2024) 140475
1000
Rotor spacing (mm)
(a)Diagrams of Cp of the upper and lower rotors under different rotor spacing
0.00000
4.0000
8.0000
12.ö0ö
16.000
20.000
(b) Comparison ofwake sfructures by depicting the Q-criterion (Q=IOO) and velocity at different rotor spacmg
Fig. 15. Simulation results and analysis of rotor spacing.
20
15
10
5
-5
-10
0=300
0=600
—0=1200
——0=1500
30
15
-15
-30
0.6
0.6
0.7
0.8
0.9
1.0
Time (s)
1.1
1.2
1.3
0.7
0.8
0.9
1.0
Time (s)
1.1
1.2
00
0=600
0=900
1200
0=1500
1.3
(a) Upper rotor torque of CRVAWT
(b) Total torque of CRVAWT
Fig. 16. The variation of torque and time of CRVAWT under different included angles.
be considered simultaneously. Therefore, in response surface optimiza-
tion, the value in power coefficient per unit height of the turbine is
chosen as the optimization objective, i.e., the ratio of Cp to the height of
the turbine L, where L 2H + d. It provides a balance between a higher
power factor and a more stable turbine.
This study adopts the second-order response model and the corre-
sponding design method of BBD. Based on the research in the previous
section, the value ranges of the four parameters and the design scheme
of four factors and three levels were determined. A total of 29 groups of
simulation experiments were carried out. The specific design scheme is
shown in
Table 3.
Solve the second-order fitting model by software calculation and
obtain the response regression model of the power coefficient:
11
===== PAGE 12 =====
P. Zheng et al.
Journal of Cleaner Production 435 (2024) 140475
cp/L= -0.089 - 2.55 X 10 4/3 + + 5.6 X 10 Sd - 4.63 X 10 60+3.1 X 10 5/3TR
(5)
+1.13 x 10 -3.85 x 10 7/30- 1.59 x 10 7TRd+7.67 x 10 8TRO-2.18 x 10 9d0
-3.54 x 10 4/32 - 3.45 x -2.93 x Io-8d2 + 1.04 x 10-702
To verify the fitting performance of the model, this study drew the
residual normal distribution probability map of the response surface, as
shown in
a. It can be observed that the residual distribution is
Fig. 17

![Figure 17](../images/vj8-fig17.jpg)
distributed along a straight line, indicating that the response surface
model has a good fitting performance.
b shows the distribution
Fig. 17
diagram of the predicted value and the actual value of the model, and it
is evident that the predicted value and the actual value are very close.
The established regression model can accurately predict the power co-
efficient of CRVAWT.
c display the relationship between the pitch angle, airfoil,
Fig. 17 —e
and power factor at different rotor spacing and included angles. These
plots provide valuable insights into the impact of different parameters
on the aerodynamic performance of a wind turbine. They can aid in
designing and optimizing wind turbines for practical applications.
After obtaining the response surface model, the response surface
needs to be evaluated. A good response surface model should have a
small coefficient of variation (CV) and a negative correlation coefficient
R2, and the corrected correlation coefficient Rä should be greater than
0.9. According to the calculation, the coefficient of variation of the
model is CV 2.07%, R2 0.96, and R2 =0.92. These values indicate
that the response surface model established in this study has a good
fitting performance and can be used to predict the power coefficient of
CRVAWT.
Using the maximum power coefficient as the optimization target, this
study obtained the optimal combination of blade parameters through
optimization algorithm calculation.
The results in
Table 4
indicate that the power coefficient of the
optimized CRVAWT is increased by 36.68%, indicating that the aero-
dynamic performance of the optimized blade through the response
Table 3
Response surface design schemes and results.
Run
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
28
29
-3
6
-3
6
-3
6
-3
6
-3
6
-3
6
15
15
21
21
18
18
18
18
18
18
18
18
15
21
15
21
18
18
18
18
15
21
15
21
18
18
18
18
18
d(mm)
500
500
500
500
265
750
265
750
500
500
500
500
265
265
750
750
265
265
750
750
500
500
500
500
500
500
500
500
500
0(0)
-30
-30
30
30
-30
-30
30
30
-30
-30
30
30
Cp/L
0.048856
0.046485
0.056856
0.054967
0.061369
0.057921
0.061859
0.058479
0.056117
0.054943
0.056287
0.055163
0.054286
0.061170
0.055811
0.058149
0.054700
0.051095
0.054670
0.054670
0.055748
0.061476
0.056708
0.062712
0.061918
0.061731
0.062476
0.062208
0.061524
cp
0.141681
0.134806
0.164881
0.159404
0.163549
0.182451
0.164853
0.184210
0.162740
0.159334
0.163233
0.159973
0.144671
0.163019
0.175804
0.183171
0.145775
0.136168
0.172210
0.172212
0.161670
0.178281
0.164453
0.181865
0.179562
0.179021
0.181179
0.180405
0.178420
surface is improved. Compared with the isolated VAWT, the optimized
CRVAWT has a single rotor power coefficient of 99.19% of VAWT, while
the total torque of the fan is only 3.04% of VAWT.
The optimized pitch angle is 1.20, which is close to 00 to achieve a
higher blade surface pressure difference and, thus, higher rotor torque in
both upwind and downwind directions. However, the fixed pitch angle
structure also reduces the cost and failure rate compared to the variable
pitch angle. The relative thickness of the optimized airfoil is 19.7%,
which is between NACA0018 and NACA0021 and is in line with the
previous simulation results. Furthermore, in terms of practical applica-
tion, the blade of the NACA0020 airfoil can be used to achieve a balance
between production cost and energy recovery efficiency. Consequently,
the optimized rotor spacing is 449.4 mm because too close a rotor pitch
will produce violent interference and reduce the wind energy recovery
efficiency of the wind turbine. While too long rotor spacing will increase
the center of gravity of the wind turbine and make the turbine unstable,
the optimized result finds a balance between power and stability. The
optimized included angle is 00, which is consistent with the best simu-
lation results. At this time, the torque between the upper and lower
rotors will be offset by each other, which plays an important role in the
stability of the offshore turbine. In terms of practical application, the
upper and lower rotors should be kept in synchronized reverse rotation
with gears or other devices. Otherwise, the torque between the rotors
may not be canceled out.
The CRVAWT can significantly improve the overall stability of the
turbine with a small difference in power factor and is less prone to
capsizing, making it very suitable for offshore wind energy recovery.
These findings provide valuable insights into the design and optimiza-
tion of wind turbines for practical applications.
In this study, the 3D model was designed by Solidworks, the
CRVAWT was simulated and analyzed by Star ccm + software, and
finally the parameters of the response surface optimized CRVAWT were
established by Design-Expert. The flow chart of this study is shown in
Fig. 18.

![Figure 18](../images/vj8-fig18.jpg)
The contra-rotating vertical axis wind turbine has overall stability
advantages and is particularly suitable for collecting wind energy on
offshore floating platforms.
illustrates the application scenario of
Fig. 19

![Figure 19](../images/vj8-fig19.jpg)
the optimized CRVAWT.
5. Conclusions
To improve the stability and power generation efficiency of
CRVAWT, the current study conducted a comprehensive simulation
analysis and parameter optimization research for CRVAWT. However,
the physical model of the CRVAET used in the simulation consists of two
rotors with opposite rotational directions on the top and bottom.
Consequently, the design optimization scheme for CRVAWT consists of
three parts: model building, parameter analysis, and response surface
optimization, as shown in
Fig. 20.

![Figure 20](../images/vj8-fig20.jpg)
The current study conducted simulation analysis for VAWT and the
simulation results of three turbulence models with experimental values
to determine the optimal turbulence model. Mesh independence anal-
ysis was used to evaluate the plotted mesh, and the simulations were
balanced between time cost and accuracy, with the difference between
the final simulated and experimental values being only 1.69%. The
simulation analysis was then performed for CRVAWT under the same
simulation environment. The power efficiency of the CRVAWT is slightly
lower compared to the isolated VAWT but has a significant advantage in
12
===== PAGE 13 =====
P. Zheng et al.
Journal of Cleaner Production 435 (2024) 140475
Normal Plot of Residuals
0.045
Predicted vs. Actual
OOSS
Actual
z
99
95
90
70
so
30
20
10
-100
Externally Studentized Residuals
210
(a) Probability diagram of residual normal distribution
(b) Predicted value and actual value of the model
(c) Response surface of B, T R, and
cp (0=-300 500, 750m)
Table 4
Optimization results of blade parameters.
(d) Response surface of B, T R, and
cp (0=00 , d=265, 500, 750m)
Fig. 17. Response surface fitting results.
(e) Response surface of ß, T R, and
cp (0=300 500, 750m)
Original
Optimized
6
1.2
21
19.7
d(mm)
270
449.4
cp
0.1344
0.1837
terms of overall torque, and the turbine is more stable.
Furthermore, a comparative analysis of CRVAWT's pitch angle,
relative airfoil thickness, pitch between rotors, and pitch angle between
rotors by analyzing the power coefficient, blade section pressure, and
blade surface pressure. Based on this study of CRVAWT's aerodynamic
performance, a four-factor, three-level response surface model with
optimized objectives and design parameters was established using Box-
Behnken's response design method. The optimal CRVAWT parameters
were obtained after optimization calculation. The main findings of the
current study are summarized as follows:
i) With the increase of pitch angle, the surface pressure difference of
the blade upwind decreases gradually, and the stlrface pressure
difference of the blade downwind area increases gradually. When
the pitch angle is 00, the surface pressure difference of the blades
is all at a higher value, and the power coefficient is highest.
ii) As the relative thickness of the airfoil increases, the pressure in
the high-pressure area of the blade surface remains almost un-
changed, while the peak pressure in the low-pressure area de-
creases and the range increases. The optimtlm relative thickness
is between 18% and 21%, and the optimization results indicate
that the optimum relative thickness is 19.7%.
iii) When the upper and lower rotors are too close to each other,
there is a strong vortex interaction between the rotors, which
affects the absorption of wind energy by the turbine.
iv) When keeping the initial phase angle at 0, the torques of the
upper and lower rotors cancel each other out, drastically reducing
the lateral force of the wind turbine.
v) The power coefficient of the optimized CRVAWT increased by
5.1.
36.68%, the total torque of the turbine was reduced by 96.96%,
and the turbine was more stable overall. These findings indicate
that the CRVAWT is well-suited for harvesting wind energy from
offshore platforms.
Limitations in this study
i) The influence of the supports is not considered in the simulation,
which may have some influence on the simulation process.
13
===== PAGE 14 =====
P. Zheng et al.
Modeling
Establish geometry model
Establish VAWT
simulation model
Journal of Cleaner Production 435 (2024) 140475
ii) The upper and lower rotors still interfere with each other, and the
power of a single rotor of the CRVAWT is reduced compared to
the isolated VAWT.
iii) Variable pitch angles may further improve wind energy recovery
efficiency.
iv) There are more parameters, such as the number and size of the
blades, the shape of the support, etc., which need to be further
investigated.
In filture studies, photovoltaic panels will be placed between the
upper and lower rotors to minimize the interactions between the rotors.
The photovoltaic panels can reduce the mutual interference between the
rotors and improve the wind energy recovery efficiency while main-
taining the overall stability of the CRVAWT. At the same time, the
SSTk. IDDES
Realizable k-c
Comparison of turbulence models
Independence analysis
Simulate
Establish CRVAWT
simulation model
Analysis parameters
Establishing a Response
Surface Model
Optimization of
Optimize
CRVAWT parameters
Fig. 18. Flow chart of CRVAWT parameter optimization method.
The optimized rotor has aP
higher power fåctor and caw
recover more wind energy
The total torque is
smaller and th
CRVAWT more stable
CRVAWT
o Oter-rotating Vertical Axis
sißulation D
et0i/
CR-
VAWT
• 9 tt0dsou
sj!ueqoan
Fig. 20. The design, optimization, and scheme of CRVAWT.
Power grid
Fig. 19. Application of the optimized CRVAWT for offshore wind energy recovery.
14
===== PAGE 15 =====
P. Zheng et al.
photovoltaic panels can collect solar energy from the environment to
further improve the energy recovery efficiency.
The research results of this study can provide a reference basis for the
research methodology and structural design of co-axial contra-rotating
vertical axis wind turbines, which is expected to promote the further
development and performance optimization of offshore vertical axis
wind turbines.
CRediT authorship contribution statement
Peng Zheng: Conceptualization, Software, Writing — original draft,
Writing — review & editing, Data curation, Visualization. Hexiang
Zhang: Resources, Validation, Writing — original draft, Writing — review
& editing. Zutao Zhang: Project administration, Supervision, Valida-
tion. Waleed Salman: Investigation, Writing —
review & editing.
Mansour Abdelrahman: Investigation, Writing — review & editing.
Declaration of competing interest
The authors declare that they have no known competing financial
interests or personal relationships that cotlld have appeared to influence
the work reported in this paper.
Data availability
Data will be made available on request.
Acknowledgments
This work was stlpported by the National Natural Fotlndation of
China under Grants No. 51975490 and by the Science and Technology
Projects of Sichuan under Grants Nos. 23QYCX0280, 2022JDRC0075,
and 2022NSFSC0461; and by the Science and Technology Projects of
Yibin under Grant No.2021ZYCG017, No. SWJTU2021020001 and
SWJTU2021020002; and by the Science and Technology Projects of
Chengdu under Grant No. 2021YF0800138GX.
Appendix A. Supplementary data
Supplementary data to this article can be found online at https://doi.
org/10.1016/j.jc1epro.2023.140475.
References
Al-Kayiem, H.H., Bhayo, B.A., Assadi, M., 2016. Comparative critique on the design
parameters and their effect on the performance of S-rotors. Renew. Energy 99,
1306-1317.
Al-Shahri, O.A., et al., 2021. Solar photovoltaic energy optimization methods, challenges
and issues: a comprehensive review. J. Clean. Prod. 284.
ANSYS Inc, 2014. Introduction to Ansys Fluent-Turbulence Modeling.
Bai, C.J., Wang, W.C., 2016. Review of computational and experimental approaches to
analysis of aerodynamic performance in horizontal-axis wind turbines (HAWTs).
Renewable Sustainable Energy Rev. 63, 506—519
Balduzzi, F., Bianchini, A., Ferrara, G., Ferrari, L., 2016. Dimensionless numbers for the
assessment of mesh and timestep requirements in CFD simulations of Darrieus wind
turbines. Energy 97, 246—261.
Bhutta, M.M.A., et al., 2012. Vertical axis wind turbine - a review of various
configurations and design techniques. Renewable Sustainable Energy Rev. 16 (4),
1926-1939.
Cuevas-Carvajal, N., Cortes-Ramirez, J.S., Norato, J.A., Hernandez, C., Montoya-
Vallejo, M.F., 2022. Effect of geometrical parameters on the performance of
conventional Savonius VAWT: a review. Renewable Sustainable Energy Rev. 161.
Day, H., Ingham, D., Ma, L., Pourkashanian, M., 2021. Adjoint based optimisation for
efficient VAWT blade aerodynamics using CFD. J. Wind Eng. Ind. Aerod. 208.
Diaz, H., Soares, C.G., 2020. Review of the current status, technology and future trends of
offshore wind farms. Ocean Eng. 209.
Didane, D.H., Rosly, N., Zulkafli, M.F., Shamsudin, S.S., 2018a. Performance evaluation
of a novel vertical axis wind turbine with coaxial contra-rotating concept. Renew.
Energy 115, 353-361
Journal of Cleaner Production 435 (2024) 140475
Didane, D.H., Rosly, N., Zulkafli, M.F., Shamsudin, S.S., 2018b. Performance evaluation
of a novel vertical axis wind turbine with coaxial contra-rotating concept. Renew.
Energy 115, 353-361
Eboibi, 0., Danao, L.A.M., Howell, R.J., 2016. Experimental investigation of the
influence of solidity on the performance and flow field aerodynamics of vertical axis
wind turbines at low Reynolds numbers. Renew. Energy 92, 474—483.
Elsakka, M.M., Ingham, D.B., Ma, L., Pourkashanian, M., 2019. CFD analysis of the angle
of attack for a vertical axis wind turbine blade. Energy Convers. Manag. 182,
154-165.
Hilewit, D., Matida, E., Fereidooni, A., el Ella, H.A., Nitzsche, F., 2019. Numerical
investigations of a novel vertical axis wind turbine using Blade Element Theory-
Vortex Filament Method (BET-VFM). Energy sci. Eng. 7 (6), 2498-2509.
Hoang, A.T., et al., 2022. Energy-related approach for reduction of C02 emissions: a
critical strategy on the port-to-ship pathway. J. Clean. Prod. 355.
https://www.globalcarbonproject.org/carbonbudget/index.htm#.
Islam, M.R., Mekhilef, S., Saidur, R., 2013. Progress and recent trends of wind energy
technology. Renewable Sustainable Energy Rev. 21, 456—468.
Jahangiri, A., et al., 2022. Coupled CFD and 3E (Energy, Exergy, and Economical)
analysis of using windbreak walls in heller-type cooling towers. J. Clean. Prod. 358.
Kouloumpis, V., Sobolewski, R.A., Yan, X.Y., 2020. Performance and life cycle
assessment of a small scale vertical axis wind turbine. J. Clean. Prod. 247.
Kumar, R., Raahemifar, K., Fung, A.S., 2018. A critical review of vertical axis wind
turbines for urban applications. Renewable Sustainable Energy Rev. 89, 281—291.
Kumar, P.M., Sivalingam, K., Lim, T.C., Ramakrishna, S., Wei, H., 2019. Review on the
evolution of Darrieus vertical Axis wind turbine: large wind turbines. Clean
Technologies 1 (1), 205-223.
Lee, H., Poguluri, S.K., Bae, Y.H., 2022. Development and verification of a dynamic
analysis model for floating offshore contra-rotating vertical-axis wind turbine.
Energy 240
Li, Qa, et al., 2016. Study on power performance for straight-bladed vertical axis wind
turbine by field and wind tunnel test. Renew. Energy 90, 291—300.
Li, S.T., et al., 2021. Experimental investigation of solidity and other characteristics on
dual vertical axis wind turbines in an urban environment. Energy Convers. Manag.
229.
Marinic-Kragic, 1., Vucina, D., Milas, Z., 2020. Computational analysis of Savonius wind
turbine modifications including novel scooplet-based design attained via smart
numerical optimization. J. Clean. Prod. 262.
Marx, J., Schreiber, A., Zapp, P., 2019. Response to 'Life-cycle greenhouse gas emissions
of onshore and offshore wind turbines'. J. Clean. Prod. 219, 33—34.
Masdari, M., Tahani, M., Naderi, M.H., Babayan, N., 2019. Optimization of airfoil Based
Savonius wind turbine using coupled discrete vortex method and salp swarm
algorithm. J. Clean. Prod. 222, 47—56.
Menter, F.R., 1994. Two-equation eddy-viscosity turbulence models for engineering
applications. AIAA J. 32 (8), 1598-1605.
Mohamed, M.H., 2012. Performance investigation of H-rotor Darrieus turbine with new
airfoil shapes. Energy 47 (1), 522—530.
Naccache, G., Paraschivoiu, M., 2018. Parametric study of the dual vertical axis wind
turbine using CFD. J. Wind Eng. Ind. Aerod. 172, 244—255.
O'meara, M., Mueller, T.J., 1987. Laminar separation bubble characteristics on an airfoil
at low Reynolds numbers. AIAA J. 25 (8), 1033—1041.
Peng, H.Y., Lam, H.F., Liu, H.J., 2019. Power performance assessment of H-rotor vertical
axis wind turbines with different aspect ratios in turbulent flows via experiments.
Energy 173, 121-132.
Poguluri, S.K., Lee, H., Bae, Y.H., 2021. An investigation on the aerodynamic
performance of a co-axial contra-rotating vertical-axis wind turbine. Energy 219
Pope, K. , Dincer, 1., Naterer, G.F., 2010. Energy and exergy efficiency comparison of
horizontal and vertical axis wind turbines. Renew. Energy 35 (9), 2102—2113.
Rezaeiha, A., Montazeri, H., Blocken, B., 2018. Towards accurate CFD simulations of
vertical axis wind turbines at different tip speed ratios and solidities: guidelines for
azimuthal increment, domain size and convergence. Energy Convers. Manag. 156,
301-316.
Sadorsky, P., 2021a. Wind energy for sustainable development: driving factors and future
outlook. J. Clean. Prod. 289.
Sadorsky, P., 2021b. Wind energy for sustainable development: driving factors and
future outlook. J. Clean. Prod. 289.
Schumann, U., 1977. Realizability of Reynolds-stress turbulence models. The Physics of
Fluids, AIP 20 (5), 721-725.
Shur, M.L., Spalart, P.R., Strelets, M.K., Travin, A.K., 2008. A hybrid RANS-LES approach
with delayed-DES and wall-modelled LES capabilities. Int. J. Heat Fluid Flow 29 (6),
1638-1649.
Song, C.G., et al., 2015. Investigation of meshing strategies and turbulence models of
computational fluid dynamics simulations of vertical axis wind turbines. J. Renew.
Sustain. Energy 7 (3).
Spalart, P.R., 1997. Comments on the Feasibility of LES for Wings and on the Hybrid
RANS/LES Approach, 1997. Proceedings of the First AFOSR International
Conference on DNS/LES, pp. 137-147.
Su, J., et al., 2020. Investigation of V-shaped blade for the performance improvement of
vertical axis wind turbines. Appl. Energy 260.
Tjiu, W., Marnoto, T., Mat, S., Ruslan, M.H., Sopian, K., 2015a. Darrieus vertical axis
wind turbine for power generation I: assessment of Darrieus VAWT configurations.
Renew. Energy 75, 50-67.
15
===== PAGE 16 =====
P. Zheng et al.
Tjiu, W., Marnoto, T., Mat, S., Ruslan, M.H., Sopian, K., 2015b. Darrieus vertical axis
wind turbine for power generation I: assessment of Darrieus VAWT configurations.
Renew. Energy 75, 50-67.
Vergaerde, A., et al., 2020. Experimental characterisation of the wake behind paired
vertical axis wind turbines. J. Wind Eng. Ind. Aerod. 206.
Journal of Cleaner Production 435 (2024) 140475
Wong, K.H., et al., 2018. 3D CFD simulation and parametric study of a flat plate deflector
for vertical axis wind turbine. Renew. Energy 129, 32—55.
Wu, X.N., et al., 2019. Foundations of offshore wind turbines: a review. Renewable
Sustainable Energy Rev. 104, 379—393.
Zhang, T., et al., 2020. A numerical study on choosing the best configuration of the blade
for vertical axis wind turbines. J. Wind Eng. Ind. Aerod. 201.
16
