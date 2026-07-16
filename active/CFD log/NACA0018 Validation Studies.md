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
## Run 1
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
Mesh
- ![[Pasted image 20260716102707.png|203]]
- refinement: inflate boundary layer, growth rate = 1.15
### Results
**Cl:** 0.174
**Cd:** 0.052 



