---
Title: "On a self-start Darrieus wind turbine: blade design and field tests"
Author: "N.C. Batista; R. Melicio; V.M.F. Mendes; M. Calderon; A. Ramiro"
Published: 2014
Created: 2026-07-02
Processed: true
tags:
- "sources"
---

# On a self-start Darrieus wind turbine: blade design and field tests

N.C. Batista a,b, R. Melicio a,b*, V.M.F. Mendes a,c, M. Calderon d, A. Ramiro d

a Departamento de Fisica, Universidade de Evora, Evora, Portugal

b IDMEC/Associated Laboratory for Energy, Transports and Aeronautics, Instituto Superior Tecnico, Universidade de Lisboa

c Department of Electrical Engineering and Automation, Instituto Superior de Engenharia de Lisboa, Lisbon, Portugal

d Department of Electrical Engineering, E.I.I., Extremadura University, Badajoz, Spain

Received 08 September 2014

* Corresponding author. Tel.: +351 266 745372; fax: +351 266 745394.

E-mail address: ruimelicio@uevora.pt (R. Melicio).

E-mail address: vfmendes@deea.isel.pt (V.M.F. Mendes).

## Abstract

This paper is about a design of an urban area Darrieus VAWT, having self-start ability due to an innovative profile design named EN0005, avoiding the need of extra components or external electricity feed-in. An approach is presented to study the ability of a blade profile to offer self-start ability. Methodologies applied for the blade body and for profile development are reported. Field tests and main conclusions are presented to persuade for the arrangement of this design.

© 2014 Elsevier Ltd. All rights reserved.

Keywords: Darrieus wind turbine; double-multiple streamtube model; performance prediction; blade profile design.

## 1. Introduction

The renewable energy share in power production has increased significantly [1-3] along with the awareness for the harm done by the anthropogenic emission of CO2 [4]. Also, decentralized power production has grown in importance, not only at the production for local consumption [5], but also for the smarter grid context [6-8] with a growing approval for urban areas. But, the wind turbulence cannot be disregarded in those areas characterized by having brisk wind directions. So, the vertical axis wind turbine (VAWT) has advantage over the horizontal axis wind turbine [9,10], for instance: insensitivity to yaw wind direction change, smaller number of components, very low sound emission, ability to generate energy from wind in skewed flows, ability to operate closer to the ground level. A VAWT is classified into three technologic types: Savonius [11], Darrieus [12] and H-rotor [13]. Although of the involvedness in the blade design and in the performance prediction, the Darrieus type is experiencing a growth in development and installation as a result of the interest for decentralizing electric energy sources located in urban areas. The advantage of VAWT over the horizontal axis wind turbine is guidance in these areas.

The Darrieus type can be classified in two kinds of turbines: curved bladed turbine, also said egg shaped turbine; and straight bladed turbine [14]. But the Darrieus type has a problem concerned with the startup, i.e., a lack on the binary has to be conveniently overcome and to get around this lack normally is needed more functionality. Functionalities have been presented in scientific literature to overcome the Darrieus natural inability to self-start, such as: external electricity feed-in, guide-vanes [15], hybrid configuration between Savonius and Darrieus VAWT [16], blade pitch optimization [17], blade form optimization [18], and specific blade profile design [19]. The use of extra components for improving self-start capabilities increases the complexity of the wind turbine, leading to higher manufacture and maintenance costs and lower sustainability.

A multidisciplinary and comprehensive study approach was carried out to study the aerodynamic behavior and the wind turbine modeling in order to develop a new Darrieus VAWT urban design, having self-start ability and without losing at a high tip speed ratio (TSR) a good performance. A new blade profile design named EN0005 is achieved by the approach offering ability to self-start without the need of extra components or external electricity feed-in. Also, a novel approach to the double multiple streamtube (DMS) mathematical model [19-22] is presented in this paper to assess the Darrieus VAWT aerodynamic behavior.

The work presented in this paper regarding the Darrieus blade profile and blade design modulation development is a convergence of other past works [22-24]. This paper also offers a new insight to the previous works, presenting several field test conducted to assess and evaluate the new patented [29] Darrieus wind turbine blade design, regarding the ability to self-start without extra components without compromising the performance at high TSR and without audible noise emissions.

The paper offers a consolidated source of knowledge regarding the development of new Darrieus wind turbines blades. At the same time a new Darrieus blade profile and design developed with the presented tools is offered. Field tests conducted to assess and evaluate the new Darrieus wind turbine design ability to self-start without compromising a good performance at high TSR and without emitting audible noise are presented.

This paper is organized as follows. Section 2 presents the novel blade profile design approach and the developed EN0005 profile. Section 3 presents the commonly used VAWT performance prediction models offering a novel approach for the DMS model. Section 4 presents the new Darrieus VAWT design. Section 5 presents the field test for the new Darrieus VAWT. Finally, Section 6 outlines the conclusions.

## Nomenclature

A: Axial force.

B1, B2, B3: Blade slice airfoil.

c: Blade profile chord.

Cd: Blade drag coefficient.

Cl: Blade lift coefficient.

Cn: Normal force coefficient.

CP: Power coefficient.

Cpr, Ct: Pressure and tangential force coefficient, respectively.

D, L: Drag and lift force, respectively.

dA'I, dA'S: Axial force on a lower and on a upper infinitesimal blade surface, respectively.

dN'I, dN'S: Normal force on a lower and a upper infinitesimal blade surface, respectively.

dN'prI: Contribution on an infinitesimal lower surface to normal force due to Cp.

dN'prS: Contribution on an infinitesimal upper surface to normal force due to Cp.

dSI, dSS: Infinitesimal lower and upper blade surface, respectively.

dT'prI: Contribution on an infinitesimal lower surface to tangential force due to Cp.

dT'prS: Contribution on an infinitesimal upper surface to tangential force due to Cp.

Fn, Ft: Normal and tangential force, respectively.

Fta: Average tangential force.

H, h: Turbine and blade airfoil height, respectively.

h: Blade airfoil height.

i: Index.

k: Value found by iteration.

N: Normal force on the profile.

Npr, Tpr: Contribution to normal and tangential force due to Cp.

n: Number of turbine blades.

P1, P2, P3, P4, P5: Blade movement path.

p, p∞: Pressure and pressure of the undisturbed wind, respectively.

Pt, Q: Mechanical power and torque of the wind turbine, respectively.

R, R': Blade movement path radius.

r: Turbine radius.

S1, S2: Turbine area slice.

LE, TE: Blade respectively leading and trailing edges.

uds, uus: Interference factor for the downstream and for the upstream, respectively.

V∞: Undisturbed wind speed.

Va, Vw: Induced velocity and wake velocity, respectively.

Vau, Vad: Induced velocity in the downstream and in the upstream, respectively.

Vc: Velocity component parallel to chord line.

Ve: Equilibrium velocity in the upstream.

Vn: Normal velocity component.

Vr: Rotor angular speed.

W: Relative flow velocity.

α: Blade angle of attack.

β: Blade angle in relation to the vertical position.

θ: Blade azimuth angle around the rotor.

ρ: Air mass per unit of volume.

ω: Rotor angular speed at the turbine.

λ: Tip speed ratio (TSR).

τw: Shear stress.

ζ: Angle of the exerted pressure in relation to the wind speed direction.

υ, υ': Minimum and maximum blade axial angles in path P4.

## 2. Blade profile design development

The aerodynamic forces exerted on the blade profile surface are the result of the viscosity effect of the wind on the blade surface, inducing a shear stress τw and a normal tension resulting from pressure distribution p [25]. Specifically an undisturbed wind at a speed V∞ arriving with an angle of attack α to a blade surface induces a force RS on the blade profile. By definition the lift force L is the force on the blade surface given by the RS component perpendicular to undisturbed wind speed V∞; and the drag force D is the RS component parallel to the V∞. By definition the normal force N is the RS component perpendicular to the blade profile chord; and the axial force A is the RS component parallel to the blade profile chord. The geometrical relation between L, D, N, A is given by a reference system rotation of the blade angle of attack α. So, L, D are respectively given by:

![Equations 1-8](va9-eq1-8.jpg)

The pressure p and the shear stress τw contributions dN'S to the normal force and dA'S to the axial force at an infinitesimal surface dSS on the blade upper profile [25] are respectively given by.

While for the blade lower profile, the contributions dN'I to the normal force and dA'I to the axial force at an infinitesimal surface dSI on the lower profile [25] are respectively given by.

The total normal force N and the total axial force A [25] are respectively the integration of (5) and (6) between the leading edge and the trailing edge, respectively given by.

### 2.1 Approach for the blade design development

The wind behavior over the blade surface in what regards the contribution to the self-start of the wind turbine is assessed by a new approach, offering the ability to rapidly assesses small blade profiles surface modifications and the contribution to the performance of the Darrieus VAWT. The wind influence over the blade surface is assessed in function of the pressure coefficient Cpr, giving a relation between the pressure of the undisturbed wind p∞ and the pressure at a certain point in the surface of the blade p [25]. The pressure coefficient is given by:

![Equations 9-15](va9-eq9-15.jpg)

The Cpr contributions to the tangential force Tpr and to the normal force Npr on an infinitesimal upper surface on the blade are respectively given by.

The Cpr contributions to the tangential force Tpr and to the normal force Npr on an infinitesimal lower surface on the blade are respectively given by.

So, the total Cpr contributions to the tangential force Tpr and to the normal force Npr of the blade are respectively given by.

The new approach assesses those Cpr contributions to the tangential force Tpr and to the normal force Npr at a finite number of segments on the blade profile surface. The approach follows the steps:

1. Discrete procedure in the blade profile surface, chose a number of segments and divide the blade profile surface in segments, as illustrated in Fig. 1;

"See Fig. 1 at the end of the manuscript".

2. Calculate using (9) the values of Cpr at each segment of the blade profile surface, values of Cpr are illustrated in Fig. 2;

"See Fig. 2 at the end of the manuscript".

3. Calculate using (10), (11), (12) and (13) the Cpr contributions to the tangential force Tpr and the normal force Npr for the upper blade surface and for the lower blade surface, the contributions are respectively illustrated in Fig. 3 and in Fig. 4;

"See Fig. 3 at the end of the manuscript".

"See Fig. 4 at the end of the manuscript".

4. Calculate using (14) and (15) the values for the total Cpr contributions to the total tangential force Tpr and to the total normal force Npr.

The new approach is able to provide assessment and comparison of blade design of the ability to provide Darrieus wind turbine with a self-start innovation.

### 2.2 Blade profile EN0005 design

Blade profile design solutions have been tested for Darrieus VAWT application, such as profiles with trapping vortex cell systems [26], thick blades [27], and modified profiles [28]. The motivation to develop a blade profile design to the Darrieus VAWT to be located in urban areas arose to give a different solution for the lack of self-start in order to technologically contribute with a enhanced solution. This new solution is the patented [29] blade profile named EN0005 shown with the segmentation in Fig. 5.

"See Fig. 5 at the end of the manuscript".

The blade profile EN0005 upper surface is a high lift surface with a slight orientation in the desired movement of the blade. The nose of the blade is in a lower position in relation to the line chord with a tip formation in the front to increase the wind flow split. The first 20% of the blade profile lower surface length is a high lift surface. The remaining surface finishes in a cup form. The cup form increases the drag force of the blade when in a stopped position in the downstream zone. The drag force decreases to a negligible value with the starting rotation of the wind turbine blades.

A comparison between the blade profile EN0005 and blade profiles NACA0018, NACA0020, NACA4418 and NACA4420 is made by applying the assessment approach for the blade design development presented before. The blade profiles designs NACA0018, NACA0020, NACA4418 and NACA4420 [30] are shown in Fig. 6.

"See Fig. 6 at the end of the manuscript".

The total Cpr contributions to the tangential force Tpr and to the normal force Npr for each blade angle of attack on the blade profiles EN0005, NACA0018, NACA0020, NACA4418 and NACA4420 are shown in Fig. 7 and in Fig. 8, respectively.

"See Fig. 7 at the end of the manuscript".

"See Fig. 8 at the end of the manuscript".

Fig. 7 shows a better capability for the blade profile EN0005 in what regards the offering of a self-start to the Darrieus VAWT. Notice that, from angle 0º to 80º and 180º to 310º this blade profile presents a better contribution to the lift force. Also, the EN0005 presents a drag force contributing for the forward movement of the Darrieus VAWT between the angles 100º and 150º and presents a lower variation in the normal force between the 70º and 180º. Although with inversed orientation for the remaining angles, the normal force is very similar to the other blade profiles.

The lift coefficient CL, drag coefficient CD and moment coefficient CM comparison between the blade profiles EN0005, NACA0018 and NACA4418 are shown in Fig. 9, in Fig. 10 and in Fig. 11, respectively.

"See Fig. 9 at the end of the manuscript".

"See Fig. 10 at the end of the manuscript".

"See Fig. 11 at the end of the manuscript".

The profile EN0005 presents a better lift coefficient between angles -60º and -10º as result of the upper surface design. Between these angles the profile EN0005 presents a lower drag coefficient. The profile EN0005 moment coefficient is higher than the other profiles presenting a peak between angles -30º and 0º.

## 3. Darrieus VAWT performance prediction models

Although of the complexity on the aerodynamic behavior of Darrieus VAWT, mathematical models have been developed [21] for performance prediction. The most common used models found in scientific literature can be classified in three categories: vortex model, cascade model and blade element momentum (BEM) model.

The flow velocities diagram of a lift-type VAWT is shown in Fig. 12.

"See Fig. 12 at the end of the manuscript".

The undisturbed wind velocity V∞ reaches the wind turbine blade profile as an induced velocity Va. The induced velocity is due to the rotor angular speed at the wind turbine Vr, given by:

![Equations 16-20](va9-eq16-20.jpg)

The blade is influenced by the contribution of the induced velocity Va and by the induced velocity due to the rotor angular speed at the wind turbine Vr in a resulting chordal velocity, i.e., velocity parallel to the chord line of the blade profile Vc, given by.

The induced velocity Va also contributes to a normal velocity, i.e., velocity in a radial direction in relation to the center of the rotor Vn, which is given by.

The relative flow velocity W is given by.

The wind flow reaches the blade at an angle of attack α that depends on Va and θ. The angle of attack α is given by.

By considering the forces acting on the blade, the tangential force coefficient Ct and the normal force coefficient Cn are respectively given by:

![Equations 21-28](va9-eq21-28.jpg)

The tangential force Ft and the normal force Fn are respectively given by.

The average tangential force Fta in function of the tangential force Ft around the rotor and the azimuth angle θ is given by.

The mechanical torque of the wind turbine Q is given by.

The mechanical power of the wind turbine is given by.

The power coefficient CP is the relation between the mechanical power of the wind turbine and the power available in the wind. The CP is given by.

### 3.1 Blade Element Momentum Model

The BEM model combines blade element theory with momentum theory, studying the flow and behavior of the air on the blades and the involved forces [17,22]. The BEM model can be further classified into: single streamtube model, multiple streamtube model and the DMS.

#### 3.1.1 Single Streamtube Model

The single streamtube (SS) model assumes that the turbine is placed inside a SS and the blades in revolution are model by an actuator disk. The effects outside the streamtube are assumed to be negligible and the wind speeds in the upstream and downstream sides of the turbine remains with a constant value. The SS model diagram is shown in Fig. 13.

"See Fig. 13 at the end of the manuscript".

The uniform velocity through the rotor is given by:

![Equations 29-33](va9-eq29-33.jpg)

where Va is the wind velocity in the actuator disc and Vw is the wake velocity.

The turbine drag force D considering the rate of change of momentum is given by.

The turbine drag coefficient CD is given by.

The CD considering (31) is given by.

The induced velocity ratio is given by.

Equation (33) with the general mathematical expressions presented in Section 3 allows predicting the torque and power coefficient of the VAWT.

#### 3.1.2 Multiple Streamtube Model

The multiple streamtube (MS) model is a variation of the SS model, where the streamtube is divided horizontally and vertically in several parallel and adjacent streamtubes independent from each other. Each stresmtube has its own undisturbed, induced and wake velocities. The single streamtube model diagram is shown in Fig. 14.

"See Fig. 14 at the end of the manuscript".

The induced velocity ration equation for of this model is given by:

![Equations 34-38](va9-eq34-38.jpg)

where k is a value found by iteration.

A comparison elaborated by Sandia National Laboratories between the Single Streamtube model and the Multiple Streamtube model (DART computer code) [31] is shown in Fig. 15.

"See Fig. 15 at the end of the manuscript".

#### 3.1.3 Double Multiple Streamtube Model

The DMS model [17] is a variation of the MS model, where the actuator disc is divided in two half cycles in tandem, representing the upstream and the downstream sides of the rotor. A DMS model diagram is shown in Fig. 16.

"See Fig. 16 at the end of the manuscript".

The actuator disc is divided in two actuator discs, each with an induced velocity. The induced velocity decreases along the axial streamtube direction, so the induced velocity in the upstream Vaui is less than the undisturbed wind velocity V∞i that arrives to the streamtube i. Between the two actuator discs there is an equilibrium induced velocity Vei < Vaui. The induced velocity in the downstream Vad < Vei.

The induced velocity in the upstream Vaui is given by.

The interference factor for the upstream is uus < 1. This factor is given by.

The equilibrium velocity in the downstream Ve is influenced by the wake velocity of the upstream and is given by.

The induced velocity in the downstream Vad is given by.

The interference factor for the downstream uds is given by:

![Equation 39](va9-eq39.jpg)

The aerodynamic behavior of the blades in the upstream side of the wind turbine will influence the induced velocity on the blades in the downstream side [17]. The undisturbed wind velocity V∞i is defined by the wind velocity profile and increases along the wind turbine height. The torque and power coefficient of the VAWT are determined by integrating the aerodynamic behaviors in all streamtubes.

The DMS model assumes the wind turbine divided in streamtubes. An interference factor uus is selected for the upstream side of a streamtube. With the undisturbed wind velocity V∞, the rotor angular speed ω, blade radius r, blade angle of attack α and local Reynolds number are found. The lift and drag coefficients are found. The blade force is then computed using the interference factor and using the aerodynamic equations previously presented. The two resulting forces are compared and a new interference factor uus is calculated until a convergence with an error of 10^-4 is reached. With the final interference factor the final torque Q and the power coefficient CP are found. An interference factor uds for the downstream streamtube side is selected and the process starts again.

For Darrieus VAWT with complex shaped blades, the DMS adds implementation challenges, motivating a new approach developed presented in Section 3.3.

A comparison elaborated by Sandia National Laboratories between the Multiple Streamtube model and the Double-Multiple Streamtube model [17] is shown in Fig. 17.

"See Fig. 17 at the end of the manuscript".

#### 3.1.4 Models comparison

The vortex model [32,33] predicts the performance of VAWT by calculating the vorticity in the wake of the blades. The blades are substituted by vortex filaments whose strengths will be determined by the blade profile coefficients, relative flow velocity and angle of attack.

The cascade model [34] prearranges the VAWT blades in vanes called cascade and positioned in identical interspaces equal to the turbine perimeter divided by the number of blades. The aerodynamic properties of the blades are calculated independently, taking in consideration the upwind and downwind sides of the rotor, their local Reynolds number and the local angle of attack.

Although, advantages and disadvantages are intimately related with the Darrieus VAWT design and installation conditions, several most used mathematical performance prediction models advantages and disadvantages are reported. A resume of those reports are presented in [21], and summarized in Table 1.

"See Table 1 at the end of the manuscript".

### 3.2 Blade profile EN0005 performance prediction at high TSR

The DMS model is used to study the EN0005 blade profile contribution to the VAWT performance at high TSR. A VAWT performance prediction is made for the blade profiles EN0005, NACA0012 and NACA0018 with a straight bladed VAWT.

A turbine with height of 4.6 m and blade radius of 2 m having five blades with a profile of 0.30 m is the used to apply the DMS model for the blade profile EN0005, NACA0012 and NACA0018. The VAWT performance prediction is evaluated with V∞ equal to 12 m/s. The performance prediction is shown in Fig. 18.

"See Fig. 18 at the end of the manuscript".

Fig. 18 allows to conclude that the wind turbine with the profile EN0005 presents a better performance for higher TSR.

### 3.3 Novel approach for the DMS model

The novel approach for the DMS model slices the wind turbine in divisions parallel to the wind flow path and analyses the blade movement path and the blade profile mutations inside the slices for each blade angle. Each slice is treated as a virtual Darrieus VAWT. Finally the resulting slices performance data are integrated. With this proposed approach is possible to have a more accurate VAWT performance analysis of complex blade form designs. Moreover, it can be easily integrated in existing CFD and CAD, augmenting the capability and value of these applications.

Two performance prediction cases are presented to explain and illustrate the main concepts. The first case deals with a Darrieus VAWT with V shaped blades shown in Fig. 19.

"See Fig. 19 at the end of the manuscript".

Fig. 19 shows that the wind turbine is going to be sliced parallel to the undisturbed wind velocity V∞ flow path. One slice example is represented as slice S1, made in the middle of the wind turbine. The blade movement path and the blade profile mutations inside the slice are analyzed during the wind flow in the path. The blade profile airfoil B1, which is the same airfoil of the blade, has a movement that follows a circular path P1 with radius R. The DMS model is applied by considering a turbine height equal to the height between slices. Another example of a slicing is S2. Again, the slice is analyzed for the blade movement path and the blade profile mutations during the wind flow in path. The blade moves another circular path P2 with a different radius R'. The airfoil is different from the airfoil of the blade, with a higher airfoil height. The height h' of this blade is a function of the angle β of the blade and of the blade airfoil height h given by:

![Equations 40-41](va9-eq40-41.jpg)

Each slice is analyzed as an independent wind turbine, allowing that the aerodynamic behavior of the wind turbine and the blade shape can be studied with more detail. Moreover, is simpler to integrate the DMS model into existing CFD and CAD applications.

The second case deals with an H-Rotor VAWT in skewed flow as shown in Fig. 20.

"See Fig. 20 at the end of the manuscript".

Fig. 20 shows an H-Rotor VAWT influenced by a wind in skewed flow. The common wind turbine blade path is represented as circular path P1 with radius R. An elliptical shaped path P3 is followed by the blade in the middle slice where the minor radius is equal to R and the major radius is equal to R'. The blade profile has different shapes depending on the blade angle in evaluation. On one hand, when the blade is close to the major radius the shape is the same as the shape in S2 of the previous case. On the other hand, when the blade is close to the minor radius the airfoil B3 has the same height h of the blade airfoil but with a different chord size c' that is related to the angle β and the blade airfoil chord c is given by.

All blade angles around the wind turbine are not analyzed for certain slices in this case, for instance, the slice in the top of the wind turbine with the path P4 has only the positions of the blade between angles υ and υ' analyzed.

The power coefficient Cp for several slices along the V shaped blade Darrieus VAWT with the profile NACA0018 at TSR equal to 3 and to 11 are respectively shown in Fig. 21 and Fig. 22.

"See Fig. 21 at the end of the manuscript".

"See Fig. 22 at the end of the manuscript".

The higher contribution for the movement of the blades comes from the extremities closer to the axis, when the TSR=3, but when the TSR=11 the major contribution comes from the mid part of the wind turbine, particularly where the wind flow finds the NACA0018, i.e., slice S1 shown in Fig. 19.

## 4. Darrieus VAWT design

The approach applied to the development of a new Darrieus VAWT follows the steps:

1. Apply the blade design development model presented in section 2.1 for the development of a new blade profile design;

2. Apply the new approach to the DMS mathematical model presented in Section 3.3 during the development of new Darrieus VAWT blade design taking as comparison the straight blade and previous developed blade designs.

This approach is the one followed for the new Darrieus VAWT patented design [29]. This design assumes the blades are constituted by three parts: a main body indicated by 1; and two blade ends indicated by 2 [29] as shown in Fig. 23.

"See Fig. 23 at the end of the manuscript".

The blade ends are specially designed for working as new lift-capable blades that extend the main blade body. These blade ends can be placed with any angle to the inside or to the outside of the rotor, and can be placed as parallel to the main blade body, as seen respectively in B or A of Fig. 23. The blades configuration in position B allows for the wind turbine taking advantage of the energy flow reaching the turbine in any vertical or horizontal angle in relation to the rotor position as shown by 4 and 5 [29] in Fig. 24.

"See Fig. 24 at the end of the manuscript".

If the blades ends are positioned to the inside of the rotor a drag increase is generated due to the augmented blade profile height, leading to an improved self-start capability. When the wind turbine reaches rotation velocities such that TSR is greater than 2, the lift forces exerted on blade ends positioned to the inside of the rotor have different directions, providing a turbine blade revolutions stability. The configuration of the blade ends can be fixed or can dynamically change during operation. Different blade main body configurations with various blade ends positions [29] are shown in Fig. 25.

"See Fig. 25 at the end of the manuscript".

## 5. Darrieus VAWT field test

The prototype of the Darrieus VAWT design developed for field test and modified taking in consideration the collected behavior information during the test has the dimensions shown in Table 2.

"See Table 2 at the end of the manuscript".

The final the prototype is shown in Fig. 26.

"See Fig. 26 at the end of the manuscript".

The test is conducted in two different environments, i.e., in urban scenario and in wind tunnel controlled environment. Field test scenarios are shown in Fig. 27.

"See Fig. 27 at the end of the manuscript".

From left to right in Fig. 27 the scenarios are: wind tunnel in Badajoz Campus of Extremadura University, Spain; Geophysics Center in Universidade de Evora, Portugal; residential area in Cabanas de Viriato, Viseu, Portugal; residential area in Povoa de Santa Iria, Lisbon, Portugal. The test is conducted to assess the behavior of the prototype. Also, sensor modules are developed for data acquisition, for instance, anemometer, rotation counter with infrared, tension and current sensor, having local processing accomplish with an Arduino board, communicating with a data collector over a low power wireless ZigBee network. Some of the sensors are shown in Fig. 28.

"See Fig. 28 at the end of the manuscript".

The collected field tests data allows to conclude that the Darrieus VAWT design has self-start without at the wind velocities of 1.25 m/s. Also, the prototype presents a stable behavior under a stress test made in wind tunnel environment with a wind velocity of 25 m/s and has not audible noise emission in urban environment. The noise field test collected data is shown in Table 3.

"See Table 3 at the end of the manuscript".

The torque during self-start is shown in Table 4.

"See Table 4 at the end of the manuscript".

The prototype presents a high torque but low rotor angular speed. The high torque help the wind turbine to work at low wind speed. The prototype rotor speed at different wind speeds is shown in Fig. 29.

"See Fig. 29 at the end of the manuscript".

## 6. Conclusions

This paper focused on the study and development of an innovation for the Darrieus VAWT presents two novel approaches for blade profile and wind turbine design: An approach for the assessment of the wind behavior over the blade surface offering ability to easily study small blade profiles surface modifications contributing to the desired behavior of the VAWT; An approach to the DMS model offering assessment of the Darrieus VAWT aerodynamic behavior.

An innovative blade profile design for Darrieus VAWT is presented and named EN0005, offering ability to self-start without the need of extra components or external electricity feed-in and without compromising a good performance at high TSR. The blade profile design is possible to be implemented with fixed or dynamically changing blade ends. Field tests presented show that the innovative Darrieus VAWT design has the ability to self-start without extra components at the wind velocities of 1.25 m/s and a stable behavior for wind velocity of 25 m/s is proved, without audible noise emission.

## Acknowledgment

This work is funded by Portuguese Funds through the Foundation for Science and Technology-FCT under the project LAETA 2015-2020, reference UID/EMS/50022/2013.

## References

[1] Narbel PA, Hansen JP. Estimating the cost of future global energy supply. Renewable and Sustainable Energy Reviews 2014;34:91-97.

[2] Sarrias-Mena R, Fernandez-Ramirez LM, Garcia-Vazquez CA, Jurado F. Improving grid integration of wind turbines by using secondary batteries. Renewable and Sustainable Energy Reviews 2014;34:194-207.

[3] Aissaoui AG, Tahour A, Essounbouli N, Nollet F, Abid M, Chergui MI. A fuzzy-PI control to extract an optimal power from wind turbine. Energy Conversion and Management 2013;65:688-696.

[4] Kandpal TC, Broman L. Renewable energy education: a global status review. Renewable and Sustainable Energy Reviews 2014;34:300-324.

[5] Al-Karaghouli A, Renne D, Kazmerski LL. Solar and wind opportunities for water desalination in the Arab regions. Renewable and Sustainable Energy Reviews 2009;13:2397-2407.

[6] Palizban O, Kauhaniemi K, Guerrero JM. Microgrids in active network management Part I: hierarchical control, energy storage, virtual power plants, and market participation. Renewable and Sustainable Energy Reviews 2014;36:428-439.

[7] Kamel RM. Effect of wind generation system types on micro-grid (MG) fault performance during both standalone and grid connected modes. Energy Conversion and Management 2014;79:232-245.

[8] Zhang L, Gari N, Hmurcik LV. Energy management in a microgrid with distributed energy resources. Energy Conversion and Management 2014;78:297-305.

[9] Ishugah TF, Li Y, Wang RZ, Kiplagat JK. Advances in wind energy resource exploitation in urban environment: A review. Renewable and Sustainable Energy Reviews 2014;37:613-626.

[10] Eriksson S, Bernhoff H, Leijon M. Evaluation of different turbine concepts for wind power. Renewable and Sustainable Energy Reviews 2008;12:1419-1434.

[11] Shigetomi A, Murai Y, Tasaka Y, Takeda Y. Interactive flow field around two Savonius turbines. Renewable Energy 2011;36:536-545.

[12] Castelli MR, Englaro A, Benini E. The Darrieus wind turbine: proposal for a new performance prediction model based on CFD. Energy 2011;36:4919-4934.

[13] Chong WT, Naghavi MS, Poh SC, Mahlia TMI, Pan KC. Techno-economic analysis of a wind-solar hybrid renewable energy system with rainwater collection feature for urban high-rise application. Applied Energy 2011;88:4067-4077.

[14] Eriksson S, Bernhoff H. Loss evaluation and design optimisation for direct driven permanent magnet synchronous generators for wind power. Applied Energy 2011;88:265-271.

[15] Takao M, Kuma H, Maeda T, Kamada Y, Oki M, Minoda A. A straight-bladed vertical axis wind turbine with a directed guide vane row - effect of guide vane geometry on the performance, Journal of Thermal Science 2009;18:54-57.

[16] Gupta R, Biswas A, Sharma KK. Comparative study of a three-bucket Savonius rotor with a combined three-bucket Savonius-three-bladed Darrieus rotor. Renewable Energy 2008;33:1974-1981.

[17] Paraschivoiu I. Wind turbine design with emphasis on Darrieus concept. Quebec: Presses Internationales Polytechnique; 2002.

[18] Bhatta P, Paluszek MA, Mueller JB. Individual blade pitch and camber control for vertical axis wind turbines. In: Proc. 7th World Wind Energy Conference, Kingston, Canada, 2008, p. 1-10.

[19] Dominy R, Lunt P, Bickerdyke A, Dominy J. Self-starting capability of a Darrieus turbine. Journal of Power and Energy 2007;221:111-120.

[20] Batista NC, Melicio R, Matias JCO, Catalao JPS. Vertical axis wind turbine performance prediction: a new approach to the double multiple streamtube model. In: Proc. International Conference on Renewable Energies and Power Quality, Santiago de Compostela, Spain, 2012, p. 1-4.

[21] Islam M, Ting DS-K, Fartaj A. Aerodynamic models for Darrieus-type straight-bladed vertical axis wind turbines. Renewable and Sustainable Energy Reviews 2008;12:1087-1109.

[22] Batista NC, Melicio R, Matias JCO, Catalao JPS. Self-start evaluation in lift-type vertical axis wind turbines: methodology and computational tool applied to asymmetrical airfoils. In: Proc. International Conference on Power Engineering, Energy and Electrical Drives, Malaga, Spain, 2011, p. 1-6.

[23] Batista NC, Melicio R, Matias JCO, Catalao JPS. New blade profile for Darrieus wind turbines capable to self-start. In: Proc. Renewable Power Generation Conference, Edinburgh, UK, 2011, p. 1-4.

[24] Batista NC, Melicio R, Matias JCO, Catalao JPS. Darrieus wind turbine performance prediction: computational modeling. In: Camarinha-Matos LM, Tomic S, Graca P, editors. Technological Innovation for the Internet of Things: Proceedings of the Doctoral Conference on Computing, Electrical and Industrial Systems, Costa da Caparica, Portugal: Springer; 2013, p. 382-391.

[25] Anderson Jr JD. Fundamentals of Aerodynamics. 3th ed. New York: McGraw-Hill; 2001.

[26] Zannetti L, Gallizio F, Ottino G. Vortex capturing vertical axis wind turbine. Journal of Physics: Conference Series 2007;75:1-10.

[27] Bourguet R, Martinat G, Harran G, Braza M. Aerodynamic multi-criteria shape optimization of VAWT blade profile by viscous approach. In: Peink J, Schaumann P, Barth S, editors. Wind Energy: Proceedings of the Euromech Colloquium, Oldenburg: Springer; 2007, p. 215-304.

[28] Kirke BK. Evaluation of self-starting vertical axis wind turbines for stand-alone applications. PhD thesis, Griffith University, Queensland, Australia; 1998.

[29] Batista NC, Melicio R, Catalao JPS. Vertical axis turbine blades with adjustable form. Patent US 2012/0163976A1; 2012.

[30] Drela M. Subsonic airfoil development system - XFOIL. Massachusetts Institute of Technology, Massachusetts, USA, 2013, <http://web.mit.edu/drela/Public/web/xfoil/>.

[31] Strickland JH. The Darrieus turbine: a performance prediction model using multiple streamtube. Report SAND 75-0431, Sandia Laboratories, USA; 1975.

[32] Gazzano R, Marini M, Satta A. Performance calculation for a vertical axis wind turbine with variable blade pitch. International Journal of Heat and Technology 2010;28:147-153.

[33] Scheurich F, Fletcher TM, Brown RE. Simulating the aerodynamic performance and wake dynamics of a vertical-axis wind turbine. Wind Energy 2011;14:159-177.

[34] Islam M, Amin MR, Ting DS-K, Fartaj A. Aerodynamic factors affecting performance of straight-bladed vertical axis wind turbines. In: Proc. ASME International Mechanical Engineering Congress and Exposition, Washington, USA, 2007, p. 331-341.

## Figure captions

Fig. 1. Blade profile segmentation.

![Fig. 1. Blade profile segmentation.](va9-fig1.jpg)

Fig. 2. Cpr at each blade profile segment.

![Fig. 2. Cpr at each blade profile segment.](va9-fig2.jpg)

Fig. 3. Cpr at one blade profile segment.

![Fig. 3. Cpr at one blade profile segment.](va9-fig3.jpg)

Fig. 4. Cpr contribution to Tpr and Npr.

![Fig. 4. Cpr contribution to Tpr and Npr.](va9-fig4.jpg)

Fig. 5. Blade profile EN0005.

![Fig. 5. Blade profile EN0005.](va9-fig5.jpg)

Fig. 6. Blade profiles NACA0018, NACA0020, NACA4418, NACA4420.

![Fig. 6. Blade profiles NACA0018, NACA0020, NACA4418, NACA4420.](va9-fig6.jpg)

Fig. 7. Cpr contribution to Tpr.

![Fig. 7. Cpr contribution to Tpr.](va9-fig7.jpg)

Fig. 8. Cpr contribution to Npr.

![Fig. 8. Cpr contribution to Npr.](va9-fig8.jpg)

Fig. 9. Lift coefficient.

![Fig. 9. Lift coefficient.](va9-fig9.jpg)

Fig. 10. Drag coefficient.

![Fig. 10. Drag coefficient.](va9-fig10.jpg)

Fig. 11. Moment coefficient.

![Fig. 11. Moment coefficient.](va9-fig11.jpg)

Fig. 12. Flow velocities diagram of a lift-type VAWT.

![Fig. 12. Flow velocities diagram of a lift-type VAWT.](va9-fig12.jpg)

Fig. 13. Single streamtube model diagram.

![Fig. 13. Single streamtube model diagram.](va9-fig13.jpg)

Fig. 14. Multiple streamtube model diagram.

![Fig. 14. Multiple streamtube model diagram.](va9-fig14.jpg)

Fig. 15. SS model and MS model comparison with experimental data [31].

![Fig. 15. SS model and MS model comparison with experimental data [31].](va9-fig15.jpg)

Fig. 16. Double-multiple streamtube model diagram.

![Fig. 16. Double-multiple streamtube model diagram.](va9-fig16.jpg)

Fig. 17. MS model and DMS model comparison with experimental data [17].

![Fig. 17. MS model and DMS model comparison with experimental data [17].](va9-fig17.jpg)

Fig. 18. Darrieus VAWT performance prediction.

![Fig. 18. Darrieus VAWT performance prediction.](va9-fig18.jpg)

Fig. 19. Novel approach to the DMS model in a V shaped Darrieus VAWT.

![Fig. 19. Novel approach to the DMS model in a V shaped Darrieus VAWT.](va9-fig19.jpg)

Fig. 20. Novel approach to the DMS model in an H-Rotor VAWT influenced by a wind in skewed flow.

![Fig. 20. Novel approach to the DMS model in an H-Rotor VAWT influenced by a wind in skewed flow.](va9-fig20.jpg)

Fig. 21. Novel approach, power coefficient vectors for several slices at TSR equal to 3.

![Fig. 21. Novel approach, power coefficient vectors for several slices at TSR equal to 3.](va9-fig21.jpg)

Fig. 22. Novel approach, power coefficient vectors for several slices at TSR equal to 11.

![Fig. 22. Novel approach, power coefficient vectors for several slices at TSR equal to 11.](va9-fig22.jpg)

Fig. 23. New Darrieus VAWT with blade ends in two different positions.

![Fig. 23. New Darrieus VAWT with blade ends in two different positions.](va9-fig23.jpg)

Fig. 24. Wind flow reaching the new Darrieus VAWT in vertical or horizontal planes.

![Fig. 24. Wind flow reaching the new Darrieus VAWT in vertical or horizontal planes.](va9-fig24.jpg)

Fig. 25. Different blade main body configurations with various blade ends positions.

![Fig. 25. Different blade main body configurations with various blade ends positions.](va9-fig25.jpg)

Fig. 26. New Darrieus VAWT design prototype.

![Fig. 26. New Darrieus VAWT design prototype.](va9-fig26.jpg)

Fig. 27. Different field tests scenarios.

![Fig. 27. Different field tests scenarios.](va9-fig27.jpg)

Fig. 28. Field test sensors.

![Fig. 28. Field test sensors.](va9-fig28.jpg)

Fig. 29. Prototype rotor speed at different wind speeds.

![Fig. 29. Prototype rotor speed at different wind speeds.](va9-fig29.jpg)

## Tables

Table 1

Darrieus VAWT mathematical performance prediction models advantages and disadvantages [21]

| Prediction Model | Advantages | Disadvantages |
| --- | --- | --- |
| Single Streamtube | Predicts the overall performance of a lightly loaded wind turbine. Very fast computational prediction. | Does not predict the wind variations across the rotor presenting disparities compared with experimental data. |
| Multiple Streamtube | Predicts the overall performance reasonably, especially when the rotor is lightly loaded. Fast computational prediction. | Some convergence problems, increasing computational time. Slight disparities with field tests, depending on the wind turbine solidity. |
| Double-Multiple Streamtube | Offers a good correlation between the performance prediction and the experimental data. | Presents convergence problems that increase computational time. Over prediction power for high solidity wind turbine and higher TSR. |
| Vortex | With the latest improvements the model presents a high correlation between the performance prediction and the experimental data. | Takes the highest computational time of all the prediction models. |
| Cascade | Reasonable overall prediction for both low and high solidity wind turbine. No convergence problems. | Takes a reasonable computation time. |

Table 2

New Darrieus VAWT design prototype dimensions

| Parameter | Value |
| --- | --- |
| Blade body height | 36,0 cm |
| Rotor height | 48,0 cm |
| Rotor radius | 17,3 cm |
| Blade profile chord | 5,3 cm |

Table 3

Field test - noise test

| Wind speed | 2,5 m/s | 5,0 m/s |
| --- | --- | --- |
| Prototype stopped at 0 m | 42,5 dB | 44,2 dB |
| 0 m | 42,5 dB | 44,2 dB |
| 1 m | 42,5 dB | 44,2 dB |
| 2 m | 42,5 dB | 44,2 dB |
| 3 m | 42,5 dB | 44,2 dB |

Table 4

Field test - torque

| Wind speed (m/s) | Force (N) | Torque (Nm) | PowerCoefficient |
| --- | --- | --- | --- |
| 1,25 | 0,2 | 0,035 | 0,416 |
| 2 | 0,4 | 0,069 | 0,321 |
| 2,25 | 0,5 | 0,087 | 0,314 |
| 3 | 0,9 | 0,156 | 0,313 |
