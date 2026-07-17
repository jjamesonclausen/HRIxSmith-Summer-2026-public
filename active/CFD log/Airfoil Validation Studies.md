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


# batch 1 (experimental)
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


# batch 2
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

# 7.17 LLM conclusion (after NACA 0012 control and STEP review)

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
