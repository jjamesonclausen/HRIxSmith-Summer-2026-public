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
## Run 1
### Set up
**External flow volume:** 10 m in all directions
**Wall boundary conditions:** slip
**Mesh:** default settings, fineness: 5
Inlet velocity: 0.6393 m/s
### Results
**Cl:** 0.194 - much too low
**Cd:** 0.059 - too high

![[Pasted image 20260713144652.png|368]]

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
**Cl:** 
**Cd:** 


![[Pasted image 20260713125718.png|338]]
Fig 1: NACA0018 coefficients of lift and drag vs angle of attack at Re = 50,000. From [Airfoil Tools](http://airfoiltools.com/airfoil/details?airfoil=naca0018-il)