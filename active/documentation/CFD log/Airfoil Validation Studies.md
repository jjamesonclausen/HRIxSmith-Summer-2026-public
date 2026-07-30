Airfoil: NACA0018
AOA: 5 deg 
Re = 50,000
Chord: 1.0 m
Density of air\*: 1.196 kg/m3
Kinematic viscosity of air\*: 1.5293-5 m2/s

\*from SimScale defaults

Re = (rho v L) / (mu)
Cl = (2L) / (rho V^2 A)
Cd = (2D) / (rho V^2 A)
A = planform area = chord * span

## Valid NACA 0018 Data

![[Pasted image 20260713125718.png|338]]
Fig 1: NACA0018 coefficients of lift and drag vs angle of attack at Re = 50,000. From [Airfoil Tools](http://airfoiltools.com/airfoil/details?airfoil=naca0018-il)

## Valid NACA 0012 Data
![[Pasted image 20260716110725.png]]


# Batch 1 (experimental)
## Run 1
### Set up
**External flow volume:** 10 m in all directions
**Wall boundary conditions:** slip
**Mesh:** default settings, fineness: 5
Inlet velocity: 0.6393 m/s
### Results
**Cl:** 0.194 - much too low
**Cd:** 0.059 - too high

## Run 2
### Set up
**External flow volume:** 10 m in all directions
**Wall boundary conditions:** slip
**Mesh:** inflate boundary layer, growth rate 1.15, other settings default
**Inlet velocity:** 0.7645 m/s
### Results
**Cl:** 0.261 -  too low
**Cd:** 0.061 - too high

## Run 3
### Set up
**External flow volume:** 10 m in all directions
**Wall boundary conditions:** slip
**Mesh:** inflate boundary layer, growth rate 1.15, hex automatic, medium fineness
**Inlet velocity:** 0.7645 m/s
### Results
**Cl:** 0.1306 - terrible (low)
**Cd:** 0.0397 - pretty close

## Run 4
### Set up
*attempt at 2D*
**External flow volume:** 10 m in X, 2 m in Y, 0.025 m in Z
**Wall boundary conditions:** slip
**Mesh:** inflate boundary layer, growth rate 1.15, hex automatic, medium fineness
**Inlet velocity:** 0.7645 m/s
### Results
flop, forgot to set up results control before running 
**Cl:** 
**Cd:** 

## Run 5
### Set up
*mostly copied set up from a community simscale study on a naca0012 airfoil*
**External flow volume:** 3 m in all direction
**Wall boundary conditions:** slip
**Mesh:** 
![[Pasted image 20260715130746.png|213]]
**Numerics:** 1 non-orthogonal corrector
**Simulation control:** end time: 1000, delta t = 1s, write control: timestep, write interval = 1000 
**Result control:** forces and moments, surface data, probe points, field calculations
**Inlet velocity:** 0.7645 m/s
### Results
**Cl:** 0.174 much too low
**Cd:** 0.052 still a bit high


# Batch 2
***new project in simscale: 7.16 airfoil vals****
## Run 1:  0018, new CAD - NADA
### Set up
Incompressible flow simulation, air
- External flow volume: (\[-3, 8], \[-4, 4], \[-4, 4])
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- A = 1m2
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Cl:** 0.177
**Cd:** 0.060 

## Run 1:  0012
### Set up
Incompressible flow simulation, air
- External flow volume: (\[-3, 8], \[-4, 4], \[-4, 4])
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- A = 1m2
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Cl:** 0.188
**Cd:** 0.045


## Run 3:  0018, inc domain - NADA
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-8, 8])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- A = 1m2
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Notes:** basically the same as previous runs
**Cl:**
**Cd:** 

## Run 4:  0018, 2D approx - ERR
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 1m2** *might be bad now that I shrunk the comp domain down to a width of 0.5 m*
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Notes:** better? but fix area and try again
**Cl:** 0.291
**Cd:** 0.026


## Run 5:  0018, 2D approx - GOOD
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Notes:** much better lift! still a little low, and drag still high but significantly closer. I am not entirely sure why reducing the width of the comp domain increased the drag so much. Would it get better if we shrink it even more? To more closely approximate 2d?
**Cl:** 0.583
**Cd:** 0.052

\*\*run 6 was a duplicate of this, but with y+ analysis turned on. The max y+ was 18.61.

## Run 7:  0018, y+ - NADA
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- **specify first layer thickness: 0.005**
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Notes:** no improvement
**Cl:** 0.583
**Cd:** 0.052


## Run 8:  0018, fineness - MIN
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, turbulence: automatic
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
Mesh:
- ![[Pasted image 20260716102707.png|203]]
- **fineness: 8!**
### Results
**Notes:** slight decrease in lift, getting closer to good drag
**Cl:** 0.515
**Cd:** 0.041

## Run 9:  0018, turb intensity - ERR
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, **turbulence: intensity = 0.001**
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
Mesh:
- ![[Pasted image 20260716102707.png|203]]
### Results
**Notes:** hmm, i seem to have lost the improved mesh settings bc y+ went up to 18 again, and this time the Cl line was oscillating at the end which is new
![[Pasted image 20260717113550.png]]
**Cl:** 0.
**Cd:** 0.0

## Run 10:  0018, turb intensity + mesh - NADA
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, **turbulence: intensity = 0.001**
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
**Mesh:**
- ![[Pasted image 20260717113826.png|234]]
- inflate boundary layer, growth rate = 1.15
### Results
**Notes:** basically no change, although the y+ was still up to 20.11 which is not good
**Cl:** 0.570
**Cd:** 0.051

## Run 11, 12:  0018, turb intensity + y+, add full res near wall - NADA 
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, **turbulence: intensity = 0.001**
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function, **Run 12: full resolution (instead of wall function)**
Advanced concepts
- Numerics: 1 non-orthogonal corrector
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
**Mesh:**
- ![[Pasted image 20260717113826.png|234]]
- **first layer size = 0.0002486**
- inflate boundary layer, growth rate = 1.15
### Results
**Notes:** Run 11: y+ still the same (20.11) and cl cd basically the same, Run 12: y+ slightly worse, cd/cl the same

## *mesh improvement attempts*

1. Keep 5 layers.
2. Change First Layer Size to about 1e-5 m.
3. Change Small feature suppression to 1e-6 m.
4. Set the airfoil wall to full resolution, not wall function.
5. Regenerate and inspect y+ again.
got an error about high non-orthogonality, seems to be centered at trailing edge

6. Keep First Layer Size = 1e-5 m.
7. Keep 5 layers.
8. Reduce Overall relative thickness from 0.4 to 0.2.
9. Remesh and check the prism maximum again.
got the same error

rounded the tail of the wing and regenerated original mesh to check y+

got it under 5, see Run 13

*learned that if you are using automatic boundary layer settings they will get overwritten by an inflate boundary layer refinement which can cause issues*

## Run 13: rounded tail, turb int. - GOOD
### Set up
Incompressible flow simulation, air
- **External flow volume: (\[-10, 15], \[-8, 8], \[-0.25, 0.25])**
- Turbulence: k-omega SST
- Time dep: steady-state
Boundary conditions
- velocity inlet, Ux = 0.7645 m/s, **turbulence: intensity = 0.001**
- pressure outlet, gauge = 0 Pa
- slip walls, top/bottom/sides
- no slip wall, airfoil faces, turbulence: wall function, **Run 12: full resolution (instead of wall function)**
Advanced concepts
- **Numerics: 2 non-orthogonal correctors**
- Simulation control
	- end time: 1000s
	- delta t: 1s
	- write control, interval: timestep, 1000
Result control:
- forces and moment coefficients
	- lift: +y, drag: +x
	- U = 0.7645 m/s
	- L = 1m
	- **A = 0.5 m2**
**Mesh:**
![[Pasted image 20260717143206.png|242]] ![[Pasted image 20260717143256.png|247]]
- **first layer size = 0.00001
- small feature repression = 0.000001 (under main menu advanced settings)
### Results
**Notes:** max y+ == 4.913, drag below goal, lift the same
**Cl:** 0.570
**Cd:** 0.028

## Run 14: same, up fineness - NADA

exact same but fineness = 7
### Results
**Notes:** max y+ == 4.924, drag pretty good (slightly low maybe), lift still low
**Cl:** 0.572
**Cd:** 0.030

## Run 15: 0012 control (same settings as 13) - PERFECT

exact same settings, fineness 5
**\*using rounded tail to reduce non-orthogonality***
### Results
**Notes:** max y+ == 5.33, cl and cd spot on
**Cl:** 0.614
**Cd:** 0.028

## 7.17 LLM thoughts

### NACA 0012 control result

Run 15 used the same settings as Run 13, including the `0.5 m` spanwise external-flow volume, `A = 0.5 m2`, `k-omega SST`, and rounded trailing edge. It produced `Cl = 0.614` and `Cd = 0.028`, which matches the AirfoilTools-based NACA 0012 target vey closely. (source: active/CFD log/Airfoil Validation Studies.md, sources/HRI2526.md)

The initial interpretation of this result was that it is strong evidence that the shared CFD workflow is broadly functioning: the domain, boundary conditions, coefficient normalization, and SST setup are unlikely to be a general cause of the NACA 0018 lift discrepancy. The control case alone did not rule out an airfoil-specific CAD or mesh issue because matching one profile does not validate a different profile, and the trailing-edge rounding could affect the two profiles differently.

### STEP comparison

The exported STEP geometry was inspected directly.

| File | Leading-edge direction in STEP | Chord | Maximum thickness | Span |
|---|---|---:|---:|---:|
| `active/CAD log/naca0012_roundtail.step` | `+x` | `1000.017 mm` | `120.036 mm` | `1000 mm` |
| `active/CAD log/naca0018_roundtail.step` | `-x` | `999.764 mm` | `180.054 mm` | `1000 mm` |

- The NACA 0012 and NACA 0018 exports face opposite directions at `0 deg` AoA, as expected. Their orientations were therefore changed within SimScale to face `-x` at `5 deg` AoA for the simulations.
- The measured chord and thickness values are consistent with nominal `1 m` NACA 0012 and NACA 0018 geometry.
- The rounded versions preserve the original overall chord and maximum thickness. Both have the same high-level topology: one closed solid, four faces, and six edges. The rounding adds spline complexity to both models equally.
- Each STEP body is physically extruded to a `1 m` span, from `z = -500 mm` to `z = +500 mm`. In SimScale, an external-flow volume spanning `z = -0.25 m` to `z = +0.25 m` was created and the airfoil body was subtracted from it. This leaves a `0.5 m` wetted airfoil section, so the coefficient reference area `A = chord x span = 1.0 m x 0.5 m = 0.5 m2` is correct for the CFD domain.

### Current conclusion

The NACA 0012 control and STEP comparison provide no evidence that the domain, reference area, SimScale orientation process, airfoil scale, nominal thickness, or shared rounded-trailing-edge CAD method is causing the NACA 0018 result of approximately `Cl = 0.57`.

Do not continue changing general simulation settings simply to force the NACA 0018 result toward the AirfoilTools value of approximately `Cl = 0.75`. Record the result as the prediction of this steady, `k-omega SST`, rounded-NACA-0018 SimScale case and report its discrepancy from AirfoilTools. A low-turbulence NACA 0018 experiment in the project sources reports substantially different low-Re behavior, including `Clmax = 0.435` at `Re = 50,000` and `3 deg`, so the AirfoilTools curve is not the only available reference and the mismatch cannot be assigned to the CFD setup alone. (source: sources/cj9.md)

> Uncertainty: this control case does not prove that the NACA 0018 AirfoilTools value is wrong, nor does it validate a sharp, ideal NACA 0018 profile because the simulated profile has a rounded trailing edge. It does establish that no currently observed shared workflow or STEP-geometry issue explains the NACA 0018 lift gap.

## Run 17: 0010 control (same settings as 13) - GOOD
same settings but very high non-orthogonality even with rounded tail (~87)
ran anyway, got Cl 0.61 (7% high) and Cd = 0.27 (correct)
## Run 19: 0015 - OK
same settings again, again bad non-orthogonality (~89)
seems like the thicker we go the less accurate it gets
Cl= 0.58, should be more like 0.68
Cd = 0.029, pretty good
## Run 20: 0018, AOA = 3 - NADA
tested same settings as Run 13 but with AOA = 3 deg, got Cl = 0.352, Cd = 0.025
according to LLM/wiki should be Cl = 0.43 ish



# Batch 3 - Julie mesh refinements 
### 1
![[Pasted image 20260723151130.png]]
![[Pasted image 20260723151102.png]]
![[Pasted image 20260723151017.png]]

### 2
went from 6 --> 15 boundary layers 
![[Pasted image 20260723153102.png]]

### 3 
changed overall thickness from 0.5 to 1 for the boundary layers 
![[Pasted image 20260723153455.png]]

### 4
changed overall thickness from 1 --> 2 for the boundary layers 
![[Pasted image 20260723153935.png]]

### 5 
changed the growth rate 1.2 --> 1.5 and changed the overall thickness from 2 --> 2.5 
![[Pasted image 20260723154246.png]]

### 6 
added surface refinement --> surface custom sizing --> default size 0.005 (which is 0.5% of the chord length - recommended by Gemini to fix the jump in cell size)
![[Pasted image 20260724094203.png]]

### 7 
added in a volume refinement box around airfoil 
![[Pasted image 20260724094733.png]]
![[Pasted image 20260724094744.png]]
### 8 
that fixed a lot of the boundary layer crushing but the wake is cut short so i expanded the box further out ( from x max of 1 to x max of 2)
![[Pasted image 20260724095233.png|471]]
![[Pasted image 20260724095249.png|470]]
### 9 
still missing some wake i am going to shift the whole box downward 
now x (.7 to 4) y (1.5 to -1.5) z (-0.5 to 0.5)
![[Pasted image 20260724101719.png|391]]
![[Pasted image 20260724101743.png|395]]
### 10 
added another volume refinement with a smaller internal box x(0.8 -0.8) y(-0.5 0.5) and z (-0.5 0.5)
kept the other larger box with the extended wake (the geometries are named Cartesian box 3 and 4 )
![[Pasted image 20260724102518.png|499]]
![[Pasted image 20260724102530.png|463]]
### 11 
re ordered the mesh tree so that the wake refinement came first ( fineness of 5) and the volume refinement around the airfoil (fineness of 6) comes second 
![[Pasted image 20260724103644.png|456]]
![[Pasted image 20260724103702.png|446]]
### 12 
fixing up the wake mesh (both were selected so it wasn't generating)
![[Pasted image 20260724104154.png|434]]
![[Pasted image 20260724104212.png|407]]
### 13 
moved the wake box over so it cut through the center of the airfoil 
![[Pasted image 20260724104948.png|496]]![[Pasted image 20260724105003.png|441]]
Did a test run to see what the residuals are looking like - about the same 
### 14 
turned off hex element core 
turned off physics based meshing 
turned off automatic boundary layers 
![[Pasted image 20260724135438.png]]![[Pasted image 20260724135456.png]]
turned of automatic boundary layers 
![[Pasted image 20260724135438.png|444]]![[Pasted image 20260724135456.png|491]]
### 16 
adding back in the boundary layers via a refinement 
15 layers with thickness of 2.5 and a growth rate of 1.5
![[Pasted image 20260724140057.png|477]]
![[Pasted image 20260724140114.png|414]]
### 17
15 layers overall thickness of 2 growth rate of 1.5 

![[Pasted image 20260724141559.png|451]]
![[Pasted image 20260724141620.png|519]]

### 18
default size ( in surface custom sizing) from 0.05 to 0.035
changed the minimum size from 0 to 0.0001
![[Pasted image 20260724142623.png|449]]
### 19 
change growth rate from 1.5 to 1.1
assigned volumes to the wake and region refinement (they had geometry primitives but i had not selected the volume as the flow region - Gemini suggested)
![[Pasted image 20260727100405.png|447]]
![[Pasted image 20260727100426.png|443]]

### 20 
making several nested refinement boxes to smooth the transition 
![[Pasted image 20260727111418.png|213]]
set the fineness to 5.5

![[Pasted image 20260727155633.png|459]]
![[Pasted image 20260727155703.png|458]]
### 21 
phil emailed an suggested to smoothen out the jump in size increase form the boundary layer to the next layer in cells as it it was to steep right now. asked ray what they would suggest from this recommendation and they said to specify the first layer thickness to be smaller 
changing the first layer settings from
![[Pasted image 20260729133728.png|220]] to ![[Pasted image 20260729133654.png|204]]
now the growth rate is not specified but ray "calculated" that this would leave a better size for the final layer 

![[Pasted image 20260729134743.png|409]]
looks like the first three layers are wayyyy to small and the last two are huge 





### alternative ideas: 
![[Pasted image 20260728143851.png|257]]
i found a new paper with the naca 0018 and for a re of 100,00 and angle of 5 they got cl of 0.6 ish so i am going to try that 
so velocity will be 1.529


changing the small feature suppression to be  0.0005 instead of 0.00005


ideas for future:

Increase Max Iterations from 1000 to 3000 -  gives the solver more time to push those residuals down
https://www.simscale.com/docs/simulation-setup/meshing/standard/#extrusion-mesh-refinement

chatting with ray - the simscale chatbot 
suggestions: 
Numerics – for stability, try changing velocity and pressure gradient schemes to Gauss‑Linear
Run longer. Keep iterating until the lift and drag curves flatten. Convergence is important before trusting coefficients (maybe change this through the max iterations thing mentioned above)
says that the inflated boundary layer settings look good 
says that lift can be too low if the solution is not fully stabilized yet so letting it run longer might fix the results 

Got it — thanks, that helps.
 final message from ray: 
If the hole is there, your geometry is correct. So this is likely **not a setup error anymore**.

At this point, the difference (0.47 vs 0.75) is usually **physical**, not a bug.

A few things to keep in mind:

- Lift coefficient depends on the exact airfoil, Reynolds number, and flow conditions
- Reference values (like 0.75) often come from experiments or specific cases
- Your simulation is a simplified model, so it won’t always match exactly

Also, your result can still be valid even if it’s different — it just means your case is different from the reference. [](https://www.simscale.com/knowledge-base/why-are-my-lift-and-drag-coefficients-too-big-small/)

So you’re not doing anything wrong here 👍

![[Pasted image 20260728151121.png]]

# Batch 4 - Anna mesh refinements

## Mesh A1 
starting with all baseline settings, changes are the following:
\**strikethroughs indicate changes made to get the mesh to generate*

algorithm: hex dom 
manual mesh sizing
min edge length: 0.00~~0~~5
max edge length: 10
auto boundary layers off
#### Refinements
##### Surface refinement 1
Levels: ~~\[7, 8]~~ \[4, 5]
no cell zone
faces: airfoil surfaces
##### Inflate boundary layer 2
layers: 10
expansion ratio: 1.2
min thickness: 0.0005
surface layer relative thickness: 0.001
faces: airfoil surfaces
##### Region refinement 3
boundaries: (\[-0.7, 1], \[-0.3. 0.3], \[-0.25, 0.25])
max edge length: 0.01

~~##### Region refinement 4
wake: (\[0, 1.5], \[-0.5. 0.5], \[-0.25, 0.25])
max edge length: 0.1~~
##### ~~Region refinement 5
large: (\[-2, 2], \[-1, 1], \[-0.25, 0.25])
max edge length: 0.5~~

## Mesh JA1
### algorithm:
standard, fineness 4
### refinements:
#### surface custom sizing 1
default size: 0.015 m
min size: 1e-4 m
#### volume custom sizing 2
outer: (\[-1, 2], \[-1.5. 1.5], \[-0.25, 0.25])
fineness: 5.5
#### volume custom sizing 3
wake: (\[0, 2], \[-0.7. 0.7], \[-0.25, 0.25])
fineness: 6.5
#### volume custom sizing 5
inner: (\[-0.7, 1], \[-0.3. 0.3], \[-0.25, 0.25])
fineness: 7
#### inflate boundary layer 5
specify growth rate
num layers: 15
relative thickness: 2
growth rate: 1.1
### Outcome:
**Max non-orthogonality:** 72.85
**Max aspect ratio:** 35.05

![[Pasted image 20260729083846.png]]![[Pasted image 20260729084006.png]]![[Pasted image 20260729084039.png]]

## Mesh JA2
### algorithm:
standard, fineness 4
### refinements:
#### surface custom sizing 1
default size: 0.015 m
min size: 1e-4 m
#### volume custom sizing 2
outer: (\[-1, 2], \[-1.5. 1.5], \[-0.25, 0.25])
fineness: 5.5
#### volume custom sizing 3
wake: (\[0, 2], \[-0.7. 0.7], \[-0.25, 0.25])
fineness: 6.5
#### volume custom sizing 5
inner: (\[-0.7, 1], \[-0.3. 0.3], \[-0.25, 0.25])
fineness: 7
#### inflate boundary layer 5
specify growth rate
**num layers: 10**
relative thickness: 2
growth rate: 1.1
### Outcome:
**Max non-orthogonality:** 72.64
**Max aspect ratio:** 16.98
![[Pasted image 20260729090114.png|268]]      ![[Pasted image 20260729090145.png|265]]  

### Simulation
note from julie's settings the airfoil surface was no-slip with a turbulence wall function, i changed it to full resolution turbulence
also, velocity was 0.765, I changed it back to 0.7645 m/s -- this may have been incorrect bc the viscosity mightve been changed so that julies velocity was correct

**Residuals:**
![[Pasted image 20260729101629.png]]

**Max y+:** 5.307

**Cl:** 0.422 bruhhhh
**Cd:** 0.036 ok

## Mesh JA3
### algorithm:
standard, fineness 4
### refinements:
#### surface custom sizing 1
default size: 0.015 m
min size: 1e-4 m
#### volume custom sizing 2
outer: (\[-1, 2], \[-1.5. 1.5], \[-0.25, 0.25])
fineness: 5
#### volume custom sizing 3
wake: (\[0, 2], \[-0.7. 0.7], \[-0.25, 0.25])
fineness: 6
#### volume custom sizing 5
inner: (\[-0.7, 1], \[-0.3. 0.3], \[-0.25, 0.25])
fineness: 6.5
#### inflate boundary layer 5
specify growth rate
**num layers: 10**
relative thickness: 2.5
growth rate: 1.5
### Outcome:
**Max non-orthogonality:** 
**Max aspect ratio:** 
### Simulation

**Residuals:**

**Max y+:** 

**Cl:** 
**Cd:** 


![[Pasted image 20260728151121.png|428]]

## Mesh JA4: Boundary-layer thickness reduction

Copied Mesh JA3 and changed only the inflate-boundary-layer relative thickness from `2.5` to `0.5`, following Phil's review. Kept the `10` layers, `1.5` growth rate, surface sizing, and volume refinements unchanged to isolate a thinner prism stack.

Purpose: retain smooth cell-size transitions while making the boundary-layer cells thinner normal to the airfoil surface.

### Outcome
max non-orthogonality - 83 
![[Pasted image 20260729220720.png|399]]

Pending mesh generation, mesh-quality inspection, solved-`y+` check, and CFD run.
