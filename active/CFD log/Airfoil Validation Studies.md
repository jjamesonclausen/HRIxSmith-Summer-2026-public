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
## Run 1:  0018
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


## Run 3:  0018
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

## Run 4:  0018
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


## Run 5:  0018
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

## Run 7:  0018
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