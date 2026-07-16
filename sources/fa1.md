---
title: "Aerodynamics of Finite Wings – Introduction to Aerospace Flight Vehicles"
source: "https://eaglepubs.erau.edu/introductiontoaerospaceflightvehicles/chapter/finite-wing-characteristics/"
author: "J. Gordon Leishman"
published: 2023-01-01
created: 2026-07-16
Processed: true
description: "<p>The overarching concept of this eBook is to provide students with a broad-based introduction to the aerospace field, emphasizing technical content while keeping the material accessible and digestible. The eBook is structured into chapters that can be aligned with one or more lecture periods. Each chapter includes detailed text, illustrations, application problems, a self-assessment quiz, and topics for further discussion. Hyperlinks to additional resources are also provided for students who want to explore each topic in greater depth.</p><p>At the end of the eBook, additional worked examples and application problems provide further opportunities for practice and review. While some chapters may be covered fully in class, others may be covered more selectively or assigned for self-study. The more advanced topics near the end of the eBook are intended primarily for self-study and as a primer for continuing students on important technical subjects such as high-speed flight, stability and control, vertical flight, and space flight. This approach helps students build a stronger foundation for future study and careers in aerospace engineering.</p>"
tags:
  - "clippings"
---
## Introduction

When the flow passes over a finite wing, i.e., a wing with a definite span from tip to tip, the downstream flow is characterized by the formation of a trailing wake system comprising swirling flows called wingtip vortices, as shown in Figure 1. These vortices resemble horizontal tornadoes and exhibit high rotational “induced” flow velocities, particularly near their centers, which extend downstream for many wing spans. The vortices left in the wing’s wake significantly affect the aircraft’s aerodynamics, primarily reducing lift and increasing drag. Wing-generated vortices will form along the edges of the wing tips (or at the end of the winglet) or wherever else on the wing there is a significant spanwise change in the pressure and lift distribution, such as at the side edges of the flaps.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2024/12/TipVortex_swirl_photo-1.png)

The vortices trailing from the wing tips produce a downwash over the wing, affecting its lift and drag.

The wingtip vortices, or *tip vortices*, produce a vertical *downwash* velocity over the wing, especially near the wingtips. This downwash is of sufficient magnitude to alter the angle of attack of every wing section and, subsequently, the amount of aerodynamic lift and drag produced on the entire wing. The type of drag caused by wingtip vortices is called *induced drag*. Consequently, finite-span wings have different aerodynamic characteristics from those of two-dimensional airfoils. The wing’s aerodynamic characteristics, such as lift and drag, depend on its shape, including chord distribution, span, spanwise twist, and other factors, including the presence of a winglet. The addition of underslung engines can also affect the spanwise lift distribution, which, in turn, further affects lift and drag.

- Appreciate the physical nature and effects of the trailed wake system behind a wing of finite span.
- Understand the essential aerodynamic characteristics of finite wings, including the effects of wing aspect ratio on lift and drag.
- Know how to interpret and use a drag polar for a finite wing and an airplane.

## Origin of Trailing Vortices

The formation of vortices behind finite wings has been studied for over a century. Frederick Lanchester conducted some of the first investigations in the early 1900s, and his [book(opens in new tab)](https://archive.org/details/aerodynamicscons00lanc) on the subject eventually led to the development of modern wing theory. By any aerodynamic standard, the formation of a tip vortex is a complex fluid-dynamic phenomenon. It is well known that, when combined with the freestream flow, the flow in the tip region moves from the lower to the upper surface and begins to rotate, forming a swirling (vortical) flow that trails behind the airplane.

The photograph in Figure 2 below illustrates this significant aerodynamic behavior, visualized by smoke injected into the wake of a Boeing 747. The strengths of these vortical flows depend on the magnitude of the pressure gradient at the wing and on the tip shape, which, in turn, affect the lift distribution on the wing. A short distance downstream of the wing’s trailing edge, the outer wing tip vortices in the photograph are rolled up rather tightly.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Boeing_747_performing_wing_vortex_trials_3-1024x812-1.jpeg)

A Boeing 747 in a NASA trailing wake study. Two dominant swirling trailing vortices, one from each wingtip, roll up behind the airplane.

To explain the underlying flow physics of tip vortex formation, it is essential to remember that a static pressure difference exists between the upper and lower surfaces, which is the source of lift on the wing. Research has shown that the tip vortex arises from the flow’s tendency to curl around the wing tips due to the pressure gradient there, as illustrated in the schematic in Figure 3. In this regard, pressure tends to equalize, causing flow to move from the higher pressure on the lower surface to the lower pressure on the upper surface. The consequence of this behavior is the initiation of a rotational motion in the flow, which marks the beginning of wingtip vortex formation.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/WingVortexRollup.png)

The wingtip vortices trail behind the wing, producing a downwash that reduces lift and increases drag.

The inherent three-dimensionality of the flow at the wing tip and the formation of the tip vortex have been extensively studied for decades. This research employs a range of experimental and computational methods, such as computational fluid dynamics (CFD), as illustrated in Figure 4. These results, which can be plotted as functions of flow velocity, pressure, and other variables, have revealed the complex aerodynamics of vortex roll-up. This roll-up process concerns the presence and interaction of three-dimensional boundary layers, flow separation, and shear layers at the wing tip. The tip vortex is usually tightly rolled up within 2 to 3 chord lengths behind the wing. It will then slowly diffuse and spin down under the action of viscosity and turbulence.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/TipVortexRollup.png)

The origin of the trailing vortex system behind a wing is a complex evolutionary process involving pressure gradients, boundary layers, and flow separation.

One research finding is that tip vortex formation is an evolutionary process. It takes some downstream distance before the vortices become fully formed behind a wing. Once created, however, they remain persistent, decaying only slowly under the action of viscosity and turbulence. Another concern is the potential impact of wingtip vortices on a following airplane, particularly near airports.

**Natural condensation of water vapor over an airplane wing**

When an airplane flies, the airflow over the wing undergoes changes in velocity, pressure, and temperature. Condensation can occur if the local static temperature falls to the dew-point temperature, producing visible vapor over the wing or in concentrated vortical regions. For steady, adiabatic flow with negligible changes in elevation, the stagnation temperature remains constant, so

$$
\[ c_p T_{\infty} + \frac{V_{\infty}^2}{2} = c_p T + \frac{V^2}{2} \]
$$

where is the specific heat at constant pressure, ${V_{\infty}}$ is the freestream velocity, is the local flow velocity, and $T_{\infty}$ and are the corresponding static temperatures. Solving for the local static temperature gives

$$
\[ T = T_{\infty} - \frac{V^2-V_{\infty}^2}{2c_p} \]
$$

Therefore, regions where the flow accelerates above the freestream velocity experience a reduction in static temperature.

If the local compression or expansion is approximately isentropic, the corresponding pressure and temperature changes are related by

$$
\[ \frac{T}{T_{\infty}} = \left( \frac{p}{p_{\infty}} \right)^{(\gamma-1)/\gamma} \]
$$

where $p_{\infty}$ and are the freestream and local static pressures, respectively, and $\gamma$ is the ratio of specific heats, approximately 1.4 for air. For condensation to occur, the local static temperature must fall to or below the dew-point temperature,, so that

$$
\[ T \leq T_d \]
$$

or, using the isentropic pressure-temperature relation,

$$
\[ T_{\infty} \left( \frac{p}{p_{\infty}} \right)^{(\gamma-1)/\gamma} \leq T_d \]
$$

This condition is most likely in humid air when substantial local pressure reductions occur over the wing, within wing-tip or flap-edge vortices, or around engine nacelles. The resulting condensation makes portions of the otherwise invisible flow field visible, as illustrated in the photograph below.  
![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/EngineVortices.png)

## Effects of Trailing Vortices

The induced velocity field from the wingtip vortices is shown in Figure 5. Near the center of the vortex, the induced velocity is relatively high. However, the induced velocity decreases inversely with distance from the vortex; by a semi-span, the effects diminish significantly. The core region of the wingtip vortex experiences more substantial viscous effects, so it rotates more like a solid body. The core is typically very small, however, of the order of 10% of the wingtip chord.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/TipVortex_swirl_both-1.png)

The induced velocity from a wingtip vortex diminishes inversely with distance from its core.

It will now be apparent that the aerodynamic effects of these rolled-up vortices (one from each wingtip) are significant. First, because of their swirling-induced flow field, they will produce a downwash at each wing section. The principle is shown in Figure 6 below. Adding the downwash flow vector to the freestream flow vector ${V_{\infty}}$ produces a resultant flow velocity (or local relative wind) that turns through an angle $\alpha_i$, called the induced angle of attack. It will be apparent from this figure that the resultant flow now approaches the wing at a different angle, creating an “effective” angle of attack, $\alpha_{\rm eff}$.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2024/12/AirfoilInducedDrag.png)

The effect of a downwash in the flow is to cause a realignment of the relative wind to the wing section, effectively tilting the lift vector aft to produce a component of drag.

From the geometry of the problem shown above, the induced angle $\alpha_i$ is given by

(1) 
$$
\begin{equation*} \alpha_i = \tan^{-1} \left( \frac{w}{V_{\infty}} \right) \end{equation*}
$$

which will, in general, be different at each station on the wing, i.e., and $\alpha_i = \alpha_i (y)$. For small angles, which are typical for a wing, it is sufficient to write that

(2) 
$$
\begin{equation*} \alpha_i = \frac{w}{V_{\infty}} \end{equation*}
$$

or, in general, that

(3) 
$$
\begin{equation*} \alpha_i (y) = \frac{w(y)}{V_{\infty}} \end{equation*}
$$

Therefore, the effective (and lower) angle of attack of the wing section is now

(4) 
$$
\begin{equation*} \alpha_{\rm eff} = \alpha - \alpha_i = \alpha - \left( \dfrac{w}{V_{\infty}} \right) \end{equation*}
$$

or, in general, that

(5) 
$$
\begin{equation*} \alpha_{\rm eff} (y) = \alpha (y) - \alpha_i(y) = \alpha(y)  - \left( \dfrac{w(y)}{V_{\infty}} \right) \end{equation*}
$$

This outcome means that the lift per unit span will be reduced relative to its two-dimensional value, i.e., the lift obtained in the absence of downwash. Notice that because will typically be much smaller than ${V_{\infty}}$, then the resultant velocity,, can be assumed to be equal to ${V_{\infty}}$, i.e.,

(6) 
$$
\begin{equation*} V_R = \sqrt{ V_{\infty}^2 + w^2} \approx V_{\infty} \end{equation*}
$$

In this situation, the lift vector changes orientation and is tilted slightly rearward relative to its direction in two-dimensional flow, thereby reducing its vertical component. Remember that the lift force, by definition, acts perpendicular to the relative wind, so in this case, it can be seen in Figure 6 that the lift vector rotates rearward through a slight angle $\alpha_i$, as does the drag. The consequence is that there is now a component of the lift that acts in the downstream direction, which is called the induced drag,, i.e.,

(7) 
$$
\begin{equation*} D'_{i} = L' \, \sin \alpha_i \approx L' \, \alpha_i \end{equation*}
$$

The induced drag component,, is often called “the drag due to lift” because its origin is primarily a consequence of the formation of the wing tip vortices, and these vortices will only form when the wing creates lift. Therefore, the higher the induced downwash from the wing tip vortices, the higher the induced drag, as illustrated in Figure 7.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/AirfoilInducedDrag_AReffect-4-scaled.png)

The total induced drag depends on the integrated effects of the induced downwash and local drag component at each wing section.

Remember that and represent forces per unit length at each section of the wing, which, in general, will be different, i.e., and. Therefore, the total lift and drag on the wing must be obtained by spanwise integration. Consequently, the total wing lift,, will be given by

(8) 
$$
\begin{equation*} L = \int_{-s}^{s} L' (y) \, dy = 2 \int_{0}^{s} L' (y) \, dy \end{equation*}
$$

where varies from at the left wing tip to at the right wing tip. Similarly, the total induced drag on the wing is given by

(9) 
$$
\begin{equation*} D_i = \int_{-s}^{s} D'_{i}(y) \, dy = \int_{-s}^{s} L' (y) \alpha_i (y)\, dy = 2 \int_{0}^{s} L' (y) \alpha_i (y)\, dy \end{equation*}
$$

## Wing Force & Moment Coefficients

When force and moment coefficients are defined for finite wings, a reference length, such as a chord length, and a reference area are needed. The reference area is typically the projected (planform) wing area,. The dimensionless coefficients for a finite wing are defined as:

Lift coefficient, $C_{L} = \displaystyle{\frac{L}{q_{\infty} S}} = \displaystyle{\frac{L}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}}$

Drag coefficient, $C_{D} = \displaystyle{\frac{D}{q_{\infty} S}} = \displaystyle{\frac{D}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}}$

Normal force coefficient, $C_{N} = \displaystyle{\frac{N}{q_{\infty} S}} = \displaystyle{\frac{N}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}}$

Axial (chord) force coefficient, $C_{A} = \displaystyle{\frac{A}{q_{\infty} S}} = \displaystyle{\frac{A}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}}$

Moment coefficient about some point, $C_{M_{a}} = \displaystyle{ \frac{M_a}{q_{\infty} \, S \, c_{\rm ref}} } = \displaystyle{ \frac{M_a}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S \, c_{\rm ref}} }$

Recall that for finite wings, it is generally the convention that the “wing area,”, is based on the *projected planform wing area* and *not* the actual (wetted) surface area. Wing area is obtained by integrating the distribution of wing chord along the span from one wing tip to the other, i.e.,

(10) 
$$
\begin{equation*} { S = \int_{-s}^{s} c \, dy = \int_{-b/2}^{b/2} c \, dy = 2 \int_{0}^{s} c \, dy = 2 \int_{0}^{b/2} c \, dy } \end{equation*}
$$

where. It is important to distinguish the wing area (symbol capital ) from the semi-span of the wing (symbol lowercase ). Notice that the reference area,, may be defined as the body’s maximum cross-sectional area for bodies such as airplane fuselages or road vehicles. Other than for wings, the reference area may not be unique, and standard conventions should always be used when defining force and moment coefficients.

Notice also in these preceding definitions of the coefficients the use of a reference length ${c_{\rm ref}}$ in the definition of the moment coefficient. For a finite wing, $c_{\rm ref}$ is usually defined as the standard mean chord (SMC) or mean aerodynamic chord (MAC). The SMC is defined as

(11) 
$$
\begin{equation*} {\rm SMC} = \overline{c} = \frac{\displaystyle{\int_{-s}^{s} c \,  dy}}{b} = \frac{2 \displaystyle{\int_{0}^{s} c \, dy}}{b} = \frac{\displaystyle{\int_{0}^{s} c \,  dy}}{s} \end{equation*}
$$

which, like the wing area, may need to be obtained by spanwise integration. The MAC is

(12) 
$$
\begin{equation*} {\rm MAC} = \overline{\overline{c}} = \frac{2 \displaystyle{\int_{0}^{s} c^2 \,  dy}}{S} \end{equation*}
$$

which, like the wing area, may need to be obtained by spanwise integration. Usually ${c_{\rm ref}} = \overline{\overline{c}}$, although in some cases ${c_{\rm ref} = \overline{c}}$ may be used. It is important to specify the definition used in any application. For rectangular wings, it will be apparent that $c_{\rm ref} = c = \overline{c} = \overline{\overline{c}}$.

Measured results for the lift coefficient,, and the drag coefficient,, are shown in Figure 8 for a wing with = 4. The tests were conducted at a low Mach number, so compressibility effects were negligible. Results for two Reynolds numbers, 700,000 and 1,000,000, are shown, obtained by varying the flow speed.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Wing_test_AR4.png)

Measured lift and drag coefficients for a wing as a function of angle of attack for a NACA 0012 wing.

The wing of a general aviation airplane has a rectangular planform with a span of 30 feet and a chord of 5.25 feet. The airplane has an in-flight weight of 2,105 lb and is cruising at a true airspeed of 120 kts at a pressure altitude of 3,000 ft, where the outside air temperature is 72 $^{\circ}$ F. Calculate the lift coefficient of the wing. Assume that the wing carries all of the lift.

Show solution/hide solution.

Because we can assume that lift = weight in level flight, i.e.,, then the lift coefficient,, is

$$
\[ C_{L} = \displaystyle{\frac{L}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}} = \displaystyle{\frac{W}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}} \]
$$

Therefore, we need to find the wing area (planform area),, and the air density in which it flies, $\varrho_{\infty}$. It is a rectangular wing, so the wing area is 30 $\times$ 5.25 = 157.5 ft. The pressure altitude is 3,000 ft with an outside air temperature of 72 $^{\circ}$ F. ISA standard temperature at 3,000 ft is 59 – 3.57 $\times$ 3 = 48.29 $^{\circ}$ F, so 23.71 $^{\circ}$ F warmer than standard. From [ISA properties](https://aerospaceweb.org/design/scripts/atmosphere/), then $\varrho_{\infty} = 0.0020706$ slug/ft. We are also given the true airspeed, ${V_{\infty}}$, in knots (kts), which must be converted to feet per second (ft/s); i.e., 120 kts = 202.54 ft/s. Therefore, the operating lift coefficient of the wing is

$$
\[ C_{L} = \displaystyle{\frac{W}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}} = \displaystyle{\frac{2,105}{\frac{1}{2} \times 0.0020706 \times 202.54^2 \times 157.5}} = 0.315 \]
$$

## Drag Polar for a Finite Wing

The net effect of these wing tip vortices on the entire wing, therefore, is a reduction in the lift (for a given angle of attack) and an increase in drag, the primary dependency being the effects of wing span and, specifically, the aspect ratio, as shown in Figure 9 in terms of the *drag polar*. These classic results, which are wind-tunnel measurements from [Ludwig Prandtl’s(opens in new tab)](https://en.wikipedia.org/wiki/Ludwig_Prandtl) original work on the subject with his students over a century ago, demonstrate that the wing’s aspect ratio significantly affects both lift and drag. Recall that the aspect ratio of the wing,, is defined as the ratio of the square of the wing span to the wing reference area, i.e.,

(13) 
$$
\begin{equation*} A\!R = \frac{{\rm span}^2}{\rm area} = \frac{b^2}{S} = \frac{4s^2}{S} = \frac{4s^2}{2 \displaystyle{\int_{0}^{s} c \, dy}} \end{equation*}
$$

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/polar_AR-1-2048x1986.png)

The effects of wing aspect ratio on the drag polar of a finite wing.

**The Wright brothers recognized the importance of aspect ratio****.**

The Wright brothers recognized the importance of aspect ratio in their 1901 wind tunnel experiments, and the results informed the design of their “Flier” in 1903. Unlike contemporaries such as Lilienthal, Whitehead, and Langley, they recognized that the ability to build and fly a high-aspect-ratio wing was crucial to successful flight, given their limited engine power. [Listen to Professor John Anderson discuss the topic of aspect ratio.](https://www.youtube.com/watch?v=2Ab6jUgTtl4)

The results in Figure 9 confirm that the aspect ratio of a wing is critically important in aerodynamic analysis because a higher lift-to-drag ratio can be obtained with wings of a higher aspect ratio, i.e., a long, slender wing with a large span relative to its average chord. The physical reason is that the higher the aspect ratio of the wing, the farther the tip vortices are away from the remainder of the wing. Therefore, the effects reduce downwash over the wing and have a smaller impact on three-dimensional aerodynamics.

A reminder of the significance of the drag polar, in this case for a finite wing, is now appropriate because it forms a basis for understanding total airplane performance. An annotated version of a representative polar is shown in Figure 10. Notice that the slope of a straight line running from the origin of the graph at (0, 0) to any point on the polar curve is the lift-to-drag ratio of the wing at that operating point.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Wing_polar.png)

Representative drag polar for a finite wing. The lift-to-drag ratio is the slope of a straight line running from the graph’s origin at (0, 0) to any point on the polar.

The *tangent point* of the line to the drag polar represents the highest slope, and so the operating point for the best lift-to-drag ratio, i.e., the best or, which can be seen to occur at one specific value of the lift coefficient for a given wing as well as its operating Reynolds number and Mach number. The value of represents the drag coefficient at zero lift. For a wing or airplane polar, it is often called the non-lifting, or zero-lift, drag coefficient and includes contributions such as skin-friction and pressure drag.

## Calculating the Lift & Drag on a Finite Wing

The lift and drag on a finite wing can be deduced from using the conservation laws in integral form. For an ideal elliptically loaded wing, the induced angle of attack, $\alpha_i$, is constant across the span, and the trailing wake has a constant downwash angle $\epsilon = 2 \alpha_i$. This result is derived from far-field wake theory, based on the [Helmholtz vortex theorems](https://en.wikipedia.org/wiki/Helmholtz%27s_theorems) and the [Biot-Savart law](https://en.wikipedia.org/wiki/Biot%E2%80%93Savart_law). Therefore, there is a vertical change in the time rate of change of momentum of the flow as it passes about the wing and turns through an angle $2 \alpha_i$. Using these principles, the force on the fluid that increases its vertical momentum can be determined, and the reaction force is then the lift on the wing.

Consider a control volume that encloses the wing and the trailing wake, within which the flow is deflected downward by a slight angle $\epsilon$, as shown in Figure 11. The mass flow rate through this streamtube is approximately $\overbigdot{m} = \varrho_{\infty} \, A_i \, V_{\infty}$, where is the effective cross-sectional area of the induced flow tube around the wing. For the ideal elliptically loaded wing, this area is approximated as

(14) 
$$
\begin{equation*} A_i = \frac{\pi b^2}{4} \end{equation*}
$$

The vertical component of the velocity imparted to the flow is $V_{\infty} \sin \epsilon$, so the force on the flow is equal to its time rate of change of vertical momentum, i.e.,

(15) 
$$
\begin{equation*} F_{\rm flow} = \overbigdot{m} \, V_{\infty} \sin \epsilon = \left( \varrho_{\infty} \, A_i \, V_{\infty} \right) V_{\infty} \sin \epsilon = \varrho_{\infty} \left( \frac{\pi b^2}{4} \right) V_{\infty}^2 \sin \epsilon \end{equation*}
$$

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/WingInducedDrag.png)

Momentum analysis of a finite wing for the ideal case of an elliptical wing.

Therefore, the lift on the wing, which is the reaction force from the fluid, is equal in magnitude to this force, i.e.,

(16) 
$$
\begin{equation*} L = \varrho_{\infty} \left( \frac{\pi b^2}{4} \right) V_{\infty}^2 \sin \epsilon \end{equation*}
$$

Assuming small angles so that $\sin \epsilon \approx \epsilon = 2 \alpha_i$, this becomes

(17) 
$$
\begin{equation*} L = \varrho_{\infty} \left( \frac{\pi b^2}{2} \right) V_{\infty}^2 \alpha_i \end{equation*}
$$

Proceeding using the standard representation of the lift in terms of the lift coefficient, then

(18) 
$$
\begin{equation*} L = \frac{1}{2} \varrho_{\infty} \, V_{\infty}^2 \, S \, C_L \end{equation*}
$$

where is the wing reference area. Equating these two expressions for lift gives

(19) 
$$
\begin{equation*} \varrho_{\infty} \left( \frac{\pi b^2}{2} \right) V_{\infty}^2 \alpha_i = \frac{1}{2} \varrho_{\infty} \, V_{\infty}^2 \, S \, C_L \end{equation*}
$$

so that

(20) 
$$
\begin{equation*} \alpha_i = \frac{S C_L}{\pi b^2} \end{equation*}
$$

Finally, because

(21) 
$$
\begin{equation*} A\!R = \frac{\text{\small span}^2}{\text{\small wing area}} = \frac{b^2}{S} \end{equation*}
$$

then the induced angle of attack of the wing is

(22) 
$$
\begin{equation*} \alpha_i = \frac{C_L}{\pi \, A\!R} \end{equation*}
$$

The rearward, or aft-pointing, component of the lift, which is the induced drag, is then obtained from force resolution. For small angles, this gives

(23) 
$$
\begin{equation*} D_i = L \, \alpha_i = L \left( \frac{C_L}{\pi \, A\!R} \right) = \frac{1}{2} \varrho_{\infty} \, V_{\infty}^2 \, S \, C_L \left( \frac{C_L}{\pi \, A\!R} \right) = \frac{1}{2} \varrho_{\infty} V_{\infty}^2 S \left( \frac{{C_L}^2}{\pi \, A\!R} \right) \end{equation*}
$$

or, in coefficient form, then

(24) 
$$
\begin{equation*} C_{D_{i}} = \frac{{C_L}^2}{\pi \, A\!R} \end{equation*}
$$

In the more general case where the wing is not elliptically loaded, then $\alpha_i$ is not the same at all points over the wing. In this case, the induced drag coefficient can be expressed as

(25) 
$$
\begin{equation*} C_{D_{i}} = \frac{(1 + \delta) \, {C_L}^2}{\pi \, A\!R} \end{equation*}
$$

where $\delta \geq 0$ is a span-loading correction factor. The theoretically best aerodynamic efficiency, corresponding to $\delta = 0$, is obtained with an elliptical spanwise lift distribution, which gives the minimum induced drag for a given lift, span, and dynamic pressure.

The effects of the trailing vortices on reducing lift on the wing have already been discussed. For an elliptically loaded wing, the induced angle of attack is

(26) 
$$
\begin{equation*} \alpha_i = \frac{C_L}{\pi \, A\!R} \end{equation*}
$$

For a non-elliptic span loading, the induced angle is not uniform along the span, but an effective correction can be introduced for preliminary estimates. Therefore, the lift coefficient for a plain finite wing can be written approximately as

(27) 
$$
\begin{equation*} C_L = C_{l_{\alpha}} \left( \alpha_{\rm eff} - \alpha_0 \right) = C_{l_{\alpha}} \left( \alpha - \alpha_0 - \alpha_i \right) \approx C_{l_{\alpha}} \left( \alpha - \alpha_0 - \frac{(1 + \delta) \, C_L}{\pi \, A\!R } \right) \end{equation*}
$$

where $C_{l_{\alpha}}$ is the two-dimensional lift-curve slope of the airfoil section that comprises the wing. Rearranging to solve for gives

(28) 
$$
\begin{equation*} C_L = \frac{C_{l_{\alpha}} \left( \alpha-\alpha_0 \right)} {1 + \displaystyle{\frac{(1 + \delta) \, C_{l_{\alpha}}}{\pi \, A\!R}}} = \left( \frac{C_{l_{\alpha}}} {1 + \displaystyle{\frac{(1 + \delta) \, C_{l_{\alpha}}}{\pi \, A\!R}}} \right) \left( \alpha-\alpha_0 \right) \end{equation*}
$$

so the lift-curve slope of the finite wing is reduced to

(29) 
$$
\begin{equation*} \frac{d C_L}{d \alpha} = \left( \frac{C_{l_{\alpha}}}{1 + \displaystyle{\frac{(1 + \delta) \, C_{l_{\alpha}}}{\pi \, A\!R}}} \right) \end{equation*}
$$

The effects are illustrated in Figure 12, where the significant reduction in the lift-curve slope with decreasing wing aspect ratio is apparent.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/cl_AR-2048x2000.png)

Results showing the effects of wing aspect ratio on the lift coefficient of a finite wing as a function of its angle of attack.

This result establishes that the lift-curve slope of a finite wing decreases as its aspect ratio decreases. It also confirms that in the limiting case where the aspect ratio becomes large and approaches infinity, the lift-curve slope approaches the two-dimensional lift-curve slope of the wing’s airfoil section, i.e.,

(30) 
$$
\begin{equation*} \frac{d C_L}{d \alpha} \longrightarrow \frac{d C_l}{d \alpha}~\mbox{\small as $A\!R \rightarrow \infty$} \end{equation*}
$$

**Prandtl’s lifting line theory**

A finite wing’s lift and induced drag in an ideal, potential, inviscid flow can also be calculated using Prandtl’s lifting-line theory. In this theory, the finite wing is replaced by a bound vortex whose circulation varies along the span, together with a trailing vortex sheet that extends downstream into the wake. The spanwise variation in circulation determines the spanwise lift distribution, and the trailing vortex sheet induces a downwash over the wing. This downwash reduces the effective angle of attack and tilts the lift vector rearward, producing induced drag.

The simplest and most important special case is an *elliptically loaded* finite wing, for which the spanwise lift distribution is elliptical. This loading produces a uniform downwash across the wing span and gives the minimum induced drag for a specified lift, span, and dynamic pressure. The induced drag coefficient is then

$$
\[ C_{D_{i}} = \frac{{C_L}^2}{\pi \, A\!R} \]
$$

This much-cited equation shows that the induced drag coefficient,, is proportional to the square of the wing lift coefficient,, and inversely proportional to the wing aspect ratio,. Therefore, for a given lift coefficient, a higher-aspect-ratio wing produces less induced drag.

In the more general case, the spanwise loading is not exactly elliptical, the downwash is not uniform, and the induced drag exceeds the ideal minimum value. The induced drag coefficient is then written as

$$
\[ C_{D_{i}} = \frac{(1 + \delta) {C_L}^2}{\pi \, A\!R} \]
$$

where $\delta \geq 0$ is a span-loading correction factor. The ideal elliptic loading gives $\delta = 0$, while any departure from this ideal loading gives $\delta > 0$.

In Prandtl’s lifting-line theory, the spanwise distribution of circulation can be represented by a Fourier sine series. The first term corresponds to the elliptic loading, and the higher-order terms represent departures from this ideal distribution. These higher-order terms increase the induced drag, and their contributions determine the value of $\delta$. In this way, lifting-line theory provides both a physical interpretation and a practical method for calculating the effects of wing planform, twist, and spanwise loading on induced drag.

Consider a finite wing with an aspect ratio of 7.2 and a span-loading correction factor $\delta = 0.1$. The wing comprises an airfoil with a two-dimensional lift-curve slope of 0.10 per degree. Calculate the lift-curve slope of the finite wing.

Show solution/hide solution.

Notice that the finite-wing lift-curve-slope formula requires the lift-curve slope to be expressed per radian. Therefore, a lift-curve slope of 0.10 per degree is the same as

$$
\[ C_{l_{\alpha}} = 0.10 \times \frac{180}{\pi} = 5.73~\mbox{\small /rad} \]
$$

The three-dimensional lift-curve slope is then calculated using

$$
\[ \frac{d C_L}{d \alpha} = \frac{C_{l_{\alpha}}}{1 + \displaystyle{ \frac{ (1 + \delta) \, C_{l_{\alpha}}}{\pi \, A\!R}}} = \frac{5.73}{1 + \displaystyle{\frac{(1 + 0.1) \times 5.73}{\pi \times 7.2}}} = 4.48~\mbox{\small /rad} \]
$$

Converting this result back to units per degree gives

$$
\[ \frac{d C_L}{d \alpha} = 4.48 \times \frac{\pi}{180} = 0.078~\mbox{\small /deg} \]
$$

Therefore, the finite-wing lift-curve slope is approximately $4.48~\mbox{\small /rad}$, or $0.078~\mbox{\small /deg}$.

## Drag Polar for an Airplane

Having developed results for the lift and drag of a finite wing, an approximate result for the drag of an entire airplane can now be established. Initially, the most straightforward approach is to develop a simple yet representative equation for use in various analyses. The simplest form can be assumed to comprise the sum of the non-lifting and lifting, or “induced,” components of drag.

Although there are other lifting surfaces on the airplane, such as the horizontal tail, these contributions can still be included in a single drag contribution, so that the drag equation can be represented approximately by

(31) 
$$
\begin{equation*} C_D = C_{D_{0}} + \frac{ {C_L}^2}{\pi \, A\!R \, e} = C_{D_{0}} + \left( \frac{1}{\pi \, A\!R \, e} \right) {C_L}^2 = C_{D_{0}} + K {C_L}^2 \end{equation*}
$$

where is the *non-lifting part*, is the *lift-dependent or induced part*, and

(32) 
$$
\begin{equation*} K = \frac{1}{\pi \, A\!R \, e} \end{equation*}
$$

Equation [31](#id1608431244) is the simplest possible representation of the airplane’s drag polar.

The factor is often known as *Oswald’s efficiency factor* after [William Bailey Oswald](http://calteches.library.caltech.edu/3961/1/Obituaries.pdf). It accounts for the loss of aerodynamic efficiency from non-ideal effects associated with a non-elliptical spanwise lift distribution, as well as the growth in profile drag on the airfoil sections comprising the wing, in aggregate, with increasing. Indeed, the value of can account for the overall airplane’s non-ideal lifting effects in aggregate.

Recall from previously that in the lower angle of attack regime, the profile drag coefficient on an airfoil section can be represented by the equation

(33) 
$$
\begin{equation*} C_d = C_{d_{0}} + d_1 \, C_l + d_2 \, {C_l}^2 \end{equation*}
$$

For a symmetric airfoil, where $\alpha_0 = 0$, then will be zero. In the case of a finite wing, the net profile drag from the airfoils that comprise the wing can be written as

(34) 
$$
\begin{equation*} C_D = C_{D_{0}} + D_1 \, C_L + D_2 \, {C_L}^2 \end{equation*}
$$

With the addition of the induced drag, the total wing drag becomes

(35) 
$$
\begin{equation*} C_D = C_{D_{0}} + D_1 \, C_L + D_2 \, {C_L}^2 + \frac{ (1 + \delta) \, {C_L}^2}{\pi \, A\!R} \end{equation*}
$$

If is assumed to be zero or small, which is typical, then

(36) 
$$
\begin{equation*} C_D = C_{D_{0}} + \left( D_2 + \frac{1 + \delta}{\pi \, A\!R} \right) {C_L}^2 \end{equation*}
$$

Comparing this result with

(37) 
$$
\begin{equation*} C_D = C_{D_{0}} + \frac{ {C_L}^2}{\pi \, A\!R \, e} \end{equation*}
$$

shows that Oswald’s efficiency factor for the wing alone is

(38) 
$$
\begin{equation*} e = \frac{1}{\pi \, A\!R \, D_2 + (1+\delta)} \end{equation*}
$$

and so the representation for becomes

(39) 
$$
\begin{equation*} C_D = C_{D_{0}} + K {C_L}^2 \end{equation*}
$$

where is given by

(40) 
$$
\begin{equation*} K = D_2 + \frac{1 + \delta}{\pi \, A\!R} = \frac{1}{\pi \, A\!R \, e} \end{equation*}
$$

In practice, however, other components of the airplane, such as the fuselage and the empennage, can affect the wing aerodynamics, so the induced-drag correction factor is usually higher than that for the wing alone. Values of for airplanes typically range from about 1.1 to 1.4, with corresponding values of varying from about 0.7 (average) to 0.9 (very good). For a wing alone, and when the lift-dependent profile-drag growth term is small, the Oswald efficiency factor reduces approximately to

(41) 
$$
\begin{equation*} e \approx \frac{1}{1 + \delta} \end{equation*}
$$

Figure 13 shows a representative drag polar. The non-lifting part is represented by the zero-lift drag coefficient,, and includes skin-friction drag, pressure or form drag, interference drag, and other drag contributions that remain when the airplane produces zero lift. The induced part is often referred to as “drag due to lift,” and its magnitude depends significantly on the wing’s operating lift coefficient.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/Aircraft_polar1.png)

The simplest representative drag polar for an airplane comprises a non-lifting part and an induced part, often called drag due to lift.

A table of representative values of and for several airplanes is shown below. Notice that because of the diversity of airplane designs within one group, it is only possible to give a range of values based on historical data. Such values are helpful in preliminary design studies of new airplanes, where the actual values may only be known after more detailed analyses, including wind tunnel or flight testing.

| Airplane type |  |  |
| --- | --- | --- |
| Twin-engine piston prop | 0.022 – 0.028 | 0.75 – 0.8 |
| Large turboprop | 0.018 – 0.024 | 0.8 – 0.85 |
| GA airplane w/retractable gear | 0.02 – 0.03 | 0.75 – 0.8 |
| GA airplane w/fixed gear | 0.025 – 0.04 | 0.65 – 0.8 |
| Subsonic jet | 0.014 – 0.02 | 0.75 – 0.85 |
| Supersonic jet | 0.02 – 0.04 | 0.6 – 0.8 |
| Sailplane | 0.012 – 0.015 | 0.8 – 0.9 |
| Drones & model aircraft | 0.02 – 0.045 | 0.75 – 0.85 |

The same general aviation airplane is flying under the conditions given in the previous example. Based on engine performance measurements, including engine rpm, manifold pressure, engine charts, and propeller efficiency, the propeller is estimated to produce 245 lb of thrust to sustain flight. Estimate the non-lifting drag coefficient,, of the aircraft.

Show solution/hide solution.

In steady, level, unaccelerated flight, the lift is equal to the airplane’s weight and the thrust required is equal to the drag, i.e., and. Therefore, if the weight of the airplane is 2,105 lb and the thrust required for flight is 245 lb, then the lift-to-drag ratio of the airplane is

$$
\[ \frac{L}{D} = \frac{2,105}{245} = 8.59 = \frac{C_L}{C_D} \]
$$

Using the value of from the previous example, the drag coefficient is

$$
\[ C_D = \frac{C_L}{L/D} = \frac{0.315}{8.59} = 0.0367 \]
$$

This result can also be confirmed directly from the definition of the drag coefficient, i.e.,

$$
\[ C_{D} = \displaystyle{\frac{D}{\frac{1}{2} \varrho_{\infty} V_{\infty}^2 \, S}} = \frac{245}{\frac{1}{2} \times 0.0020706 \times 202.54^2 \times 157.5} = 0.0367 \]
$$

Using the induced-drag form of the airplane drag polar,

$$
\[ C_D = C_{D_{0}} + \frac{{C_L}^2}{\pi \, A\!R \, e} \]
$$

For a fixed-gear general aviation airplane, the table above suggests a representative value of. The aspect ratio of this rectangular wing is

$$
\[ A\!R = \frac{b}{c} = \frac{30.0}{5.25} = 5.71 \]
$$

Therefore,

$$
\[ C_D = C_{D_{0}} + \frac{{0.315}^2}{\pi \times 5.71 \times 0.75} = C_{D_{0}} + 0.00736 = 0.0367 \]
$$

and so

This value seems reasonable based on the representative values for a fixed-gear general aviation airplane given in the table above.

## Thrust Required for Flight

As previously derived, if the simplest form of drag coefficient variation for an airplane is assumed, i.e., using

(42) 
$$
\begin{equation*} C_D = C_{D_{0}} + K {C_L}^2 = C_{D_{0}} + \frac{ {C_L}^2}{\pi \, A\!R \, e} \end{equation*}
$$

then the total drag on an airplane can be calculated as a function of its airspeed. Remember that is the aspect ratio of the wing, and the value of, Oswald’s efficiency factor, is always less than unity in any practical case.

Another way of writing this latter equation is

(43) 
$$
\begin{equation*} C_D = C_{D_{0}} + C_{D_{i}} \end{equation*}
$$

where is the induced drag coefficient, often called “drag due to lift,”

(44) 
$$
\begin{equation*} C_{D_{i}} = \frac{ {C_L}^2}{\pi \, A\!R \, e} \end{equation*}
$$

The total dimensional drag on the airplane is then

(45) 
$$
\begin{equation*} D = \frac{1}{2} \varrho_{\infty} V_{\infty}^2 S \left( C_{D_{0}} + \frac{ {C_L}^2}{\pi \, A\!R \, e} \right) \end{equation*}
$$

which must be equal to the thrust needed from the propulsive system when lift equals weight, i.e., in trimmed, steady, unaccelerated flight, then lift = weight and thrust = drag, i.e.,

(46) 
$$
\begin{equation*} L = W\quad \mbox{\small and} \quad T = D \end{equation*}
$$

The lift coefficient can be calculated because

(47) 
$$
\begin{equation*} L = W = \frac{1}{2} \varrho_{\infty} \, V_{\infty}^2 \, S \, C_L \end{equation*}
$$

so solving for gives

(48) 
$$
\begin{equation*} C_L = \frac{2 W}{\varrho_{\infty} V_{\infty}^2 S} \end{equation*}
$$

This latter equation shows that for a given wing, the value of is higher at low airspeeds and lower at higher airspeeds, and also increases with airplane weight. Of course, the maximum attainable lift coefficient is determined by the type of wing, which will reach a point at higher angles of attack when it stalls; the corresponding airspeed is called the *stall speed*.

Therefore, the drag on the airplane, and hence the thrust required for flight, is

(49) 
$$
\begin{equation*} D = T = \frac{1}{2} \varrho_{\infty} V_{\infty}^2 S C_{D_{0}} + \frac{1}{2} \varrho_{\infty} V_{\infty}^2 S \left( \frac{2 W}{\varrho_{\infty} V_{\infty}^2 S} \right)^2 \left( \frac{1}{\pi \, A\!R \, e} \right) \end{equation*}
$$

and after some rearrangement, then

(50) 
$$
\begin{equation*} D = T = \left( \frac{1}{2} \varrho_{\infty} S C_{D_{0}} \right) V_{\infty}^2 + \left( \frac{2 W^2}{\varrho_{\infty} S \left( \pi \, A\!R \, e \right)} \right) \frac{1}{V_{\infty}^2} \end{equation*}
$$

For a constant weight and density $\varrho_{\infty}$, i.e., at a given altitude, it will be apparent that this equation is of the form

(51) 
$$
\begin{equation*} D = T = A V_{\infty}^2 + \frac{B}{V_{\infty}^2} \end{equation*}
$$

where

(52) 
$$
\begin{equation*} A = \frac{1}{2} \varrho_{\infty} S C_{D_{0}} \quad \mbox{\small and} \quad B = \frac{2 W^2}{\varrho_{\infty} S \left( \pi \, A\!R \, e \right)} \end{equation*}
$$

are constants for a given airplane weight, altitude, and configuration.

This form of the drag variation, and hence the corresponding thrust required for flight, is shown in Figure 14. Notice that according to Eq. [51](#id2674482974), the non-lifting drag increases with the square of the airspeed, while the induced drag decreases inversely with the square of the airspeed. The resulting drag curve takes on a distinctive “U-shape,” with the minimum drag, and hence the minimum thrust required, occurring at an intermediate airspeed.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/Aircraft_drag.png)

Representative drag curve for an airplane in level flight has a distinctive U-shape, with a minimum drag at an intermediate airspeed. After reaching this minimum point, the drag grows quickly with increasing airspeed.

The corresponding power required for flight is

(53) 
$$
\begin{equation*} P_{\rm req} = T V_{\infty} \end{equation*}
$$

which is of the form

(54) 
$$
\begin{equation*} P_{\rm req} = A V_{\infty}^3 + \frac{B}{V_{\infty}} \end{equation*}
$$

At higher airspeeds, more power, and hence more fuel, is required for flight because the non-lifting contribution to power increases with the cube of airspeed.

Consider a flying-wing airplane with a wing reference area of 210 m <sup>2</sup>, an aspect ratio of 10, and an Oswald’s efficiency factor of 0.90. For this simplified estimate, assume that the airplane has an equivalent non-lifting drag coefficient of. The airplane’s mass is 50,000 kg. If the airplane is flying at a density altitude of 3 km and the true airspeed is 230 m/s, then calculate the total drag on the airplane.

Show solution/hide solution.

The air density at a density altitude of 3 km is 0.90925 kg m <sup>-3</sup> when using the ISA model. In steady, level, unaccelerated flight, the lift is equal to the airplane’s weight, i.e.,

$$
\[ L = W = m \, g = 50,000 \times 9.81 = 490,500~{\mbox N} \]
$$

The lift is given by

$$
\[ L = \frac{1}{2} \varrho \, V^2 \, S \, C_L \]
$$

so the operating lift coefficient of the airplane is

$$
\[ C_L = \frac{L}{ \frac{1}{2} \varrho \, V^2 \, S} \]
$$

Inserting the known values gives

$$
\[ C_L = \frac{490,500 }{0.5 \times 0.90925 \times 230.0^2 \times 210.0} = 0.097 \]
$$

Using the airplane drag polar,

$$
\[ C_D = C_{D_{0}} + \frac{{C_L}^2}{\pi \, A\!R \, e} \]
$$

then

$$
\[ C_D = 0.015 + \frac{0.097^2}{\pi \times 10.0 \times 0.90} = 0.0153 \]
$$

Therefore, the total drag force is

$$
\[ D = \frac{1}{2} \varrho \, V^2 S C_D = 0.5 \times 0.90925 \times 230.0^2 \times 210.0 \times 0.01533 \approx 77,440~\mbox{N} \]
$$

which gives a corresponding lift-to-drag ratio of

$$
\[ \frac{L}{D} = \frac{490,500}{77,440} \approx 6.33 \]
$$

## Generalization of the Airplane Drag Polar

The drag produced on an airplane will also be a function of the Reynolds number and flight Mach number. Therefore, another generalization of the prior approach is to write that

(55) 
$$
\begin{equation*} C_D = C_{D_{0}}(Re, M_{\infty}) + D_1 (Re, M_{\infty}) C_L + D_2 (Re, M_{\infty}) {C_L}^2 \end{equation*}
$$

Again, the challenge is evaluating the values of the coefficients; this usually involves a combination of wind tunnel measurements and flight tests.

Usually, for flight Mach numbers above about 0.3, compressibility effects become increasingly important, and the Mach-number dependence of the drag polar must be considered explicitly. For preliminary estimates over a limited range of Reynolds numbers, the Reynolds-number dependence is often treated as secondary, giving

(56) 
$$
\begin{equation*} C_D = C_{D_{0}}(M_{\infty}) + D_1 (M_{\infty}) \, C_L + D_2 (M_{\infty}) \, {C_L}^2 \end{equation*}
$$

Finally, the foregoing equations apply to an airplane in which the minimum drag is achieved at zero lift. If this is not the case, then a further generalization is to use

(57) 
$$
\begin{equation*} C_D = C_{D_{\rm min}} + K \left( C_L - C_{L_{\rm min~drag}} \right)^2 \end{equation*}
$$

as shown in Figure 15.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/Aircraft_polar2.png)

Generalization of the drag polar for an airplane. This form is typically more suitable for flights at higher subsonic Mach numbers.

## Winglets

The purpose of winglets is to increase the effective aspect ratio of the wing but without significantly increasing the wing’s span. The classic “Whitcomb” winglet moves the tip vortices from the wing tip to the top of the winglet, as confirmed in Figure 16. The consequence is that the tip vortices are further away from more of the wing, reducing the magnitude of the induced downwash all over the wing and decreasing its induced drag. The flow velocities induced by the tip vortices decrease inversely with distance, so even a small winglet can decrease the downwash velocities over the wing, measurably reducing drag.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/WInglet_flow.png)

Confirmation that a “tip vortex” forms at the tip of a winglet, which is rendered visible by natural condensation.

Today, airplanes have winglets either by design or retrofitted after delivery. The motivation is evident in that a winglet can reduce drag and save fuel. While the winglet adds some structural weight and produces a small increment in skin friction drag, the reductions in induced drag outweigh these concerns. Fuel savings can offset the cost of retrofitting a winglet to an airliner in as little as two years. Therefore, using a winglet makes more sense than redesigning the wing for a higher span and aspect ratio.

A large “Jumbo” airliner’s feasible wingspan and aspect ratio may be limited for several reasons, including higher wing weight and the potential for aeroelastic issues. Airport operations, such as taxiway access, parking, and hangar size, also impose additional factors. The [Boeing 777X(opens in new tab)](https://www.boeing.com/commercial/777x/) is unique because of its extremely high wingspan and aspect ratio; it uses a folding wing tip design, as shown in Figure 17. The idea is to provide an ultra-high-aspect-ratio wing for flight while maintaining a reduced wing span on the ground; therefore, a winglet to boost the wing’s effective aspect ratio is unnecessary.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/1024px-777X_Roll-Out_40407369583.jpg)

The Boeing 777X has an ultra-high aspect ratio wing. The extra-long wingspan necessitates folding the wingtips for safe ground operations.

There is no simple universal closed-form formula that predicts the aerodynamic benefit of a winglet for all wing and winglet designs. In preliminary performance estimates, however, a common approach is to represent the effect of the winglet by an empirical correction to the wing aspect ratio, such as

(58) 
$$
\begin{equation*} A\!R_{\rm eff} = A\!R \left( 1 + K_{\rm wl} \, \frac{h_{\rm wl}}{s} \right) \end{equation*}
$$

where $A\!R_{\rm eff}$ is the “effective” or corrected aspect ratio, $h_{\rm wl}$ is the length or height of the winglet, as shown in Figure 18, and $K_{\rm wl}$ is an empirical coefficient that depends on the type of winglet.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/WingWinglet_alt.png)

A winglet increases the effective aspect ratio of the wing with little or no increase in wing span.

For a classic Whitcomb winglet, it is usually assumed in Eq. [58](#id4265537072) that $K_{\rm wl} = 0.95$, at least for preliminary design or airplane performance estimates. The lifting or induced component of the drag can then be written as

(59) 
$$
\begin{equation*} C_{D_{i}} = \frac{ {C_L}^2}{\pi \, A\!R_{\rm eff} \, e} \end{equation*}
$$

While winglets present some additional surface area to the flow and somewhat increase the profile (non-lifting) drag, the benefits are realized over the range of lift coefficients during flight, as shown in Figure 19. Lift-to-drag curves for airplanes tend to be quite “peaky,” although the range of lift coefficients over which high lift-to-drag ratios can be maintained can be widened by careful airfoil and wing design. In this regard, the ability to maintain aerodynamic efficiency over a broader range of airspeeds, weights, and altitudes can be realized.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Wing_wingletpolar.png)

The improvements in the lift-to-drag ratio obtained using a winglet may be small, but fuel savings over the life of the airplane can be significant.

While the increase in lift-to-drag ratio using a winglet may only be a few percent relative to a baseline wing, the reductions in thrust required for a given airspeed can translate into substantial reductions in fuel burn during each flight. Actual fuel savings will depend on the aircraft type, flight length, and typical operating conditions. However, studies and industry data indicate that winglets can deliver significant fuel savings.

For example, a Boeing 737 equipped with blended winglets has been reported to achieve an average fuel savings of around 4% compared to the same airplane without winglets. Other modern airliners use carefully designed wingtip devices for the same purpose, namely to reduce induced drag and improve cruise efficiency. The upshot is that winglets and related wingtip devices can measurably extend an airliner’s flight range and/or increase its payload capacity.

While these performance benefits and resulting fuel savings might seem relatively modest, the high fuel consumption of commercial airliners and the large number of flights they operate mean that even a slight improvement in fuel efficiency can yield significant cost savings for airlines. Over the life of a commercial jetliner, which can exceed 25 years, the fuel savings can amount to millions of dollars for a single airplane. Therefore, fuel savings for a fleet of airliners at just one airline can reach tens or even hundreds of millions of dollars.

## Effects of Compressibility & Wing Sweep

One issue to remember is that a wing’s drag increases rapidly as the flight Mach number approaches the transonic regime due to the development of shock waves and wave drag. However, such effects are difficult to generalize because the drag depends critically on the specific wing geometry (especially its thickness and sweepback angle) and operating lift coefficient.

Figures 20 and 21 show representative wind tunnel measurements of the minimum (non-lifting) drag on semi-span wings with different sweepback angles, ${\Lambda}$, and different thickness-to-chord ratios,. For a given sweepback angle, reducing the thickness-to-chord ratio generally reduces the transonic and supersonic wave-drag penalty. However, the wing cannot simply be made as thin as possible because thickness is also needed for structural depth, stiffness, fuel volume, and practical high-lift design. Significant drag benefits can also be realized by using sweepback, especially in the transonic and supersonic regimes.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Cd0_vs_Mach_lam-2048x1871.png)

The effects of wing thickness and sweepback angle on the non-lifting drag of a semi-span wing in transonic and supersonic flow.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Cd0_vs_mach_tc-2048x1937.png)

The effects of thickness-to-chord ratio on the non-lifting drag of a semi-span wing in transonic and supersonic flow.

An approximate equation that quantifies the increase in drag resulting from the formation of shock waves and the associated wave drag is known as Lock’s fourth-power rule.[^1] The model has seen refinements and other developments by engineers over the years, but its basic form remains useful for preliminary estimates. The Lock model requires a value of the critical Mach number of the wing, $M_{\rm crit}$, which is the flight Mach number at which the maximum local Mach number first reaches unity. Lock argued that the drag associated with the shock wave scales with the third power of the Mach number increment above the critical Mach number, i.e., with ${(M_{\infty} - M_{\rm crit})^3}$. The height or extent of the shock wave also scales approximately with $M_{\infty} - M_{\rm crit}$. The net result is a wave-drag increment proportional to the fourth power, i.e., $(M_{\infty} - M_{\rm crit})^4$. A constant then appears in the final expression for the wave-drag increment, $\Delta C_{D_{w}}$, i.e.,

(60) 
$$
\begin{equation*} \Delta C_{D_{w}} = \left\{ \begin{array}{ll} 0 & \mbox{for } M_{\infty} < M_{\rm crit} \\[8pt] k_w \left( M_{\infty} - M_{\rm crit} \right)^4 & \mbox{for } M_{\infty} \geq M_{\rm crit} \end{array} \right. \end{equation*}
$$

Therefore, including this explicit wave-drag increment, the drag equation for the airplane can be written as

(61) 
$$
\begin{equation*} C_D = C_{D_{0}} + D_1 \, C_L + D_2 \, {C_L}^2 + \Delta C_{D_{w}} \end{equation*}
$$

where,, and represent the baseline drag-polar coefficients, which may also vary with Mach number.  
While the Lock equation can give useful preliminary estimates of the extra wave drag, quantitative predictions for specific airplanes depend strongly on the empirical value of. Without more detailed information, a value is often used for preliminary estimates for transport-type airplanes designed to cruise in transonic flight, where $0.7 \le M_{\rm crit} \le 0.8$. For thinner, highly swept, or supersonic-oriented configurations, a lower value, such as, is sometimes used for preliminary estimates, but should ultimately be based on wind tunnel data, flight test data, or higher-fidelity aerodynamic analysis.

## Examples of Airplane Drag Polars

A combination of calculations (possibly using CFD), wind tunnel measurements, and flight tests can define the drag polar to an acceptable degree of fidelity for performance evaluations and other applications. Drag polars have been published for various types of airplanes, including general aviation, gliders, commercial, and military aircraft. One purpose of publishing such results is to allow engineers and analysts to validate their modeling and use it for instructional purposes.

An example of a complete drag polar for a legacy commercial airplane, shown in Figure 22, is at higher subsonic Mach numbers and into the transonic domain. First, notice the increase in the zero-lift drag coefficient with increasing Mach number. Second, notice the more rapid growth in the drag as transonic conditions are approached and established (i.e., for $M_{\infty} > 0.76$). This is the consequence of exceeding the critical Mach number and the development of shock waves, which leads to a commensurate increase in wave drag.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/B727polar-2048x1975.png)

Drag polars for a commercial airplane at subsonic and transonic flight Mach numbers.

Another example of a drag polar is that of a legacy military fighter aircraft, as shown in Figure 23. In this case, the results are presented for subsonic, transonic, and supersonic flight conditions. Again, the rapid increase in drag is apparent as transonic conditions are encountered and supersonic flight is approached. Notice that the airplane has a lift-to-drag ratio of only about 3 in supersonic flight. For military airplanes, maneuvering performance is often presented in related forms, such as drag, required thrust, or excess power, as functions of load factor, because the lift required in a turn increases in proportion to.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/FigherPolarqpc-2048x1994.png)

Drag polars for a military fighter airplane for subsonic, transonic, and supersonic flight Mach numbers.

The drag coefficient of a particular airplane design is described by the equation

$$
\[ C_D = 0.04 + \left( \frac{1.26}{\pi \, A\!R} \right) {C_L}^2 \]
$$

where is the aspect ratio of the wing. For aspect ratios of 10 and 20, determine the best lift-to-drag ratio of the airplane and the lift coefficient at which this occurs.

Show solution/hide solution.

The drag coefficient for the airplane is given by

$$
\[ C_D = 0.04 + \left( \frac{1.26}{\pi \, A\!R} \right) {C_L}^2 = A + B {C_L}^2 \]
$$

where

$$
\[ A = 0.04 \quad \mbox{\small and} \quad B = \frac{1.26}{\pi \, A\!R} \]
$$

The best lift-to-drag ratio is obtained by maximizing, or equivalently by minimizing. Therefore,

$$
\[ \frac{C_D}{C_L} = \frac{A}{C_L} + B C_L \]
$$

Differentiating this expression with respect to gives

$$
\[ \frac{d (C_D/C_L)}{d C_L} = -\frac{A}{{C_L}^2} + B \]
$$

At the minimum value of,

$$
\[ -\frac{A}{{C_L}^2} + B = 0 \]
$$

so the lift coefficient for the best lift-to-drag ratio is

$$
\[ C_L = \sqrt{ \frac{A}{B} } = \sqrt{ \frac{0.04 \pi \, A\!R}{1.26} } \]
$$

For, the value of for the best is

$$
\[ C_L = \sqrt{ \frac{0.04 \pi \, A\!R}{1.26} } = \sqrt{ \frac{0.04 \times \pi \times 10 }{1.26} } = 1.00 \]
$$

and substituting this value gives

$$
\[ \frac{C_L}{C_D} = \frac{C_L}{0.04 + \left(1.26/\pi A\!R\right){C_L}^2} = \frac{1.00}{0.04 + \left(1.26/(\pi \times 10)\right) 1.00^2} = 12.48 \]
$$

For, the value of for the best is

$$
\[ C_L = \sqrt{ \frac{0.04 \pi \, A\!R}{1.26} } = \sqrt{ \frac{0.04 \times \pi \times 20 }{1.26} } = 1.41 \]
$$

and substituting this value gives

$$
\[ \frac{C_L}{C_D} = \frac{C_L}{0.04 + \left(1.26/\pi A\!R\right){C_L}^2} = \frac{1.41}{0.04 + \left(1.26/(\pi \times 20)\right) 1.41^2} = 17.65 \]
$$

## Center of Pressure & Aerodynamic Center

The procedures for finding the center of pressure and aerodynamic center on a finite wing are similar to those for two-dimensional airfoils. Recall that, by definition, the center of pressure on a wing is a *point about which the pitching moments are zero*, i.e., a point where the resultant forces can be assumed to act. The aerodynamic center is a point where *the moment is constant and independent of the angle of attack*. Determining the aerodynamic center, like the center of pressure, requires lift and moment coefficients as functions of angle of attack about any other point, usually the 1/4-chord point.

In the case of the center of pressure, then

(62) 
$$
\begin{equation*} \frac{x_{\rm cp}}{c_{\rm ref}} \simeq \frac{1}{4} - \frac{C_{M_{c_{\rm ref}/4}}}{C_L} \end{equation*}
$$

Because the center of pressure is a moving point, it is not used much in practice to resolve the forces and moments on a wing.

If the aerodynamic center is assumed to be at a distance behind the leading edge, then

(63) 
$$
\begin{equation*} C_{M_{a}} = C_{M_{\rm ac}} - C_{L} \left( \frac{x_{\rm ac}}{c_{\rm ref}} - \frac{a}{c_{\rm ref}} \right) \end{equation*}
$$

Differentiating the above equation with respect to gives

(64) 
$$
\begin{equation*} \frac{d C_{M_{a}}}{dC_{L}} = \frac{d C_{M_{\rm ac}}}{dC_{L}} - \left( \frac{x_{\rm ac}}{c_{\rm ref}} - \frac{a}{c_{\rm ref}} \right) \end{equation*}
$$

After rearrangement then

(65) 
$$
\begin{equation*} \frac{x_{\rm ac}}{c_{\rm ref}} = \frac{a}{c_{\rm ref}} - \frac{d C_{M_{a}}}{dC_{L}} \end{equation*}
$$

The value of can be obtained from

(66) 
$$
\begin{equation*} \frac{d C_{M_{a}} }{ d C_L} = \left( \frac{ d C_{M_{a}}}{d \alpha}\right) \left( \frac{d \alpha}{d C_{L}}\right) \end{equation*}
$$

This latter process is performed by finding the slopes of the best straight-line fits to the graphs of versus the angle of attack of the wing, ${\alpha}$, and versus ${\alpha}$. If the moment data are measured about the quarter-chord point of the reference chord, then $a/c_{\rm ref} = 1/4$ and.

## Vortex Wake Upsets

When viewed from the front of the airplane, the tip vortex from the left wing tip rotates clockwise, and the right one rotates counterclockwise, as the photograph in Figure 24 suggests. The vortices tend to be strongest when the airplane is heavy, slow, and producing a high lift coefficient, conditions often encountered during takeoff and landing. As the tip vortices trail back from the wing tips, they descend behind the wing under their self-induced velocities.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2022/07/Goldilocks_11053003234.jpeg)

Natural flow visualization of the wake behind a landing airplane, showing the signature of the wing tip vortices left in the cloud patterns.

While wing tip vortices affect the airplane that generates them, a concern is their persistence and potential effects on the following airplane. The generic name used for the impact of the vortex wake, especially by pilots and the FAA, is called [*wake turbulence* (opens in new tab)](https://www.faa.gov/air_traffic/publications/atpubs/aim_html/chap7_section_4.html). Wingtip vortices tend to be relatively strong and persistent and can remain for up to several minutes and many miles after the passage of an airplane through a given part of the sky. The persistence of the vortices also depends on the winds and other environmental factors, such as atmospheric turbulence.

Because the wingtip vortices persist and can take many minutes to dissipate, they can pose a concern for the following airplane, particularly in the terminal area. Additionally, the local downwash velocities may be a significant fraction of the airplane’s airspeed, accompanied by steep downwash gradients. This potential hazard is significant because it will affect the angle of attack and, consequently, the lift generated by the wing.

Notice from Figure 25 that an airplane may end up flying more perpendicularly or parallel to the wing tip vortices. On the one hand, flying nearly perpendicular to the vortices will cause the airplane to encounter an abrupt upwash followed by a downwash and then another upwash. This trajectory can cause significant changes in the airplane’s load factor during flight, which may concern passengers who experience a distinct “bump.” On the other hand, if an airplane flies parallel to the vortices, there is a tendency for the airplane to roll, which is a bad outcome. Hence the name [vortex wake upsets(opens in new tab)](https://en.wikipedia.org/wiki/Wake_turbulence) becomes clear.

![](https://eaglepubs.erau.edu/app/uploads/sites/4/2021/08/Airplane_vortexupsets.png)

Because of the persistence of the wing tip vortices, they can pose a concern for the following airplane, particularly in the terminal area where the separation between airplanes may be less than a couple of miles.

The possibility and problems of wake upsets during takeoff and landing operations became much more acute starting in the 1970s with the introduction of wide-body or [jumbo jets(opens in new tab)](https://en.wikipedia.org/wiki/Wide-body_aircraft) such as the Boeing 747 and McDonnell-Douglas DC-10. The higher weights of these airplanes produced intense and persistent wingtip vortices that caused many “wake turbulence” incidents. Smaller airplanes were particularly vulnerable and, in severe encounters, could be rolled inverted by the wake.

Subsequently, aviation authorities have required wake-turbulence separation criteria in terminal airspace, with larger spacing applied when a following aircraft may encounter the wake of a heavier or wake-generating aircraft. These procedures have greatly reduced the likelihood of wake-turbulence upsets. However, increasing separation distances between aircraft can limit the number of aircraft that can land and take off within a given time, which can seriously constrain aircraft movements at busy airports.

## Summary & Closure

The aerodynamics of wings of finite span depend critically on their aspect ratio. The higher the aspect ratio, the lower the induced component of the drag. Induced drag is an inevitable consequence of lift generation and is highest when the wing operates at higher lift coefficients, thereby creating the strongest wing tip vortices. These vortices produce a downwash flow over the wing, altering lift and drag at each wing section. Therefore, the design of finite wings for low induced drag also depends on the spanwise lift distribution. An elliptical spanwise lift distribution gives the ideal minimum induced drag for a specified lift and span, although practical wings may depart from this ideal for structural, stall, control, or manufacturing reasons.

<iframe src="about:blank" frameborder="0" title="Aerodynamics of Finite WIngs"></iframe>

- Calculate the potential improvement in lift-to-drag ratio for a wing when making a design change in the aspect ratio from 5 to 7 while keeping the same wing area. Make any reasonable assumptions.
- It is said that a winglet increases the wing’s effective aspect ratio without an increase in its span. Discuss why.
- The drag polar for a high-speed airplane shows a general reduction in the slope of the curves when approaching and exceeding Mach 1. Discuss why this behavior occurs.
- Why does the aspect ratio of a wing become less important at supersonic speeds?
- Wake-turbulence separation criteria reduce the likelihood of wake upsets, especially when a following aircraft may encounter the wake of a larger or heavier aircraft, but they can also reduce airport capacity. Discuss.

To understand more about the aerodynamics of finite wings, explore some of these online resources:

- Listen to Professor John Anderson discuss: [The Wright Brothers Discover Aspect Ratio.](https://www.youtube.com/watch?v=2Ab6jUgTtl4)
- Great educational film on: [The Secret of Flight 8: The Induced Drag.](https://www.youtube.com/watch?v=aP8jvyD1Ovc)
- To see more on vortex wake-induced drag, check out this [animation and explainer.](https://howthingsfly.si.edu/aerodynamics/vortex-drag)
- Read an interesting [journal paper](https://opg.optica.org/oe/fulltext.cfm?uri=oe-28-3-4286&id=426472) on the measurement of vortex wakes.
- A [YouTube video](https://www.youtube.com/watch?v=dfY5ZQDzC5s) showing aircraft wakes from natural condensation effects.

---

[^1]: The original work was published in the report: [The Ideal Drag Due to a Shock Wave Parts I and II](https://reports.aerade.cranfield.ac.uk/bitstream/handle/1826.2/3677/arc-rm-2512.pdf?sequence=1&isAllowed=y), ARC Report 2512 (1951), by C. N. H. Lock.
