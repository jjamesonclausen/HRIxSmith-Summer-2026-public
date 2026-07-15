## HRI2526 all things CFD
- general notes
	- had trouble with boundary layer meshing which significantly decreased the reliability of the cfd
	- ended up using simscale's physics-based mesh with three layers, overall relative thickness 0.4, growth rate 1.5
		- unstructured, prob uses wall functions, but they couldn't plot y+ values to determine if they were correct
		- future work should directly resolve the boundary layer and use a hybrid mesh
	- validated cfd using a naca airfoil and a classical savonius vawt
	- incompressible flow bc vawts operate at low wind speeds so density changes in air are negligible
	- from savonius validation studies
		- lift and drag vectors have to be set in the correct orientation
			- lift force is NOT z direction towards rotor shaft but instead INTO the blades and with MRF, the lift vector gets "moved" around in approximated time frames
		- reference areas and reference lengths within the force and moment coefficient calculations must be correct
		- correct axis of rotations centered about the rotor are important
- boundary conditions
	- inlet velocity of 2 m/s with 5% turbulence intensity
	- outlet, zero gauge pressure
	- sides/top/bottom, symmetry planes (?) to reduce comp cost
	- turbine blades subtracted from flow volume, surfaces no-slip
- turbulence models
	- RANS (reynolds-averaged navier stokes)
		- time averaged flow properties  -> effect of turbulent eddies
		- fast and cheap, best for when large-scale turbulent structures are not the primary interest
		- bad for flow instabilities, vortex shedding, transient phenomena
		- k-epsilon
			-  good for fully turbulent flow far from walls, or if cost is a major constraint
			- bad for vawts bc bad at big pressure gradients and boundary layer separation
		- k-omega, k-omega SST (shear stress transport)
			- good for wall bounded functions and flows with strong boundary layer effects, adverse pressure gradients, or mild flow separation
			- resolve all the way to the wall, but need fine mesh near wall so more expensive
			- SST version switches to k-epsilon in the free stream to reduce sensitivity to freestream turbulence properties
				- also improved flow separation and pressure gradients
				- best for vawt bc good power coefficients and torque prediction and reasonably close to experimental data and wake characteristics across TSRs
				- ideal for design exploration and parametric studies
	- LES (large eddy simulations)
		- spacially filter out smallest scale turbulence and resolve large scales w the most energy directly
		- much higher fidelity than RANS, more expensive, need very fine mesh and small time steps to handle large eddies
		- captures transient flow structures
		- good for acoustics, combustion, and flows with very large separation which RANS cant do very well
		- usually only used in fundamental research, benchmarking studies or simple geometry simulations
	- hybrids (eg DES, detached eddy simulation)
		- DES uses RANS in boundary layer near walls and LES in areas with separating flow and large eddies
- meshing
	- types of meshes
		- structured 
			- grid pattern
			- allows for precise control of cell quality
			- computationally efficient
			- ideal for boundary layer region around vawt airfoils bc you need orthogonal cells and smooth cell transitions
			- difficult and time consuming to generate
		- unstructured 
			- triangles in 2D or tetrahedra in 3D
			- more flexible which helps with complex and irregular geometries (vawts)
			- can be automatically generated
			- computationally expensive
			- lower quality cells if not generated carefully
				- can impact solver convergence and reduce solution accuracy
		- hybrid 
			- use structured mesh near blade surface to capture boundary layer
			- flexible unstructured mesh for the rest of the computational domain
			- gives high fidelity results in critical flow regions while minimizing cost
			- most common (and best) for vawts
	- non-dimensional wall distance, y+ 
		- represents the distance from the wall to the center of the first mesh cell, normalized by viscous scales
	- boundary layer meshing (near vawt blades), method depends on turbulence model
		- directly resolving the boundary layer uses a very fine mesh to compute turbulence viscous effects in the boundary layer with no approximations
			- requires y+ <= 1 to capture flow details
			- high accuracy, high cost
			- often necessary for K omega SST which needs a fine mesh too
			- often necessary for vawts (esp w dynamic stall) in general to capture boundary layer development and separation for prediction torque and cp
		- wall modeling fucntions approximate near wall behavior
			- lower cost bc dont need fine mesh near wall
			- less accurate
			- 30 < y+ < 300
			- can be used for k epsilon turbulence models that are fine with coarser near wall meshes
- rotation simulation
	- Multiple Reference Frames (MRF)
		- steady state approx using a rotating reference frame that modifies the governing equations in the rotating zone to simulate the rotation of the turbine
		- mesh is not rotated
		- less expensive than transient models
		- dont capture unsteady phenomena like dynamic stall, wake interaction, vortex shedding
		- can be used for initial vawt design iterations but not good for hi fi studies
	- Arbitrary Mesh Interface (AMI)
		- fully transient simulation that creates a mesh interface btwn moving and stationary mesh regions
		- physically rotates the rotating domain at each time step, interpolating at the interface to allow for realistic movement
		- expensiveeee
		- considers transient effect
		- better for hi fi vawt studies
	- rotating domain is usually a cylinder that encompasses the turbine blades (diameter 1.5 times the turbine diameter)
- results
	- convergence plots - good for numerical stability visualization to see if the simulation is running correctly
	- residuals? what are these
		- should drop and converge to 10e-4 for a well performing, accurate model per rec from Tom Ramsay at HALO
- TSR analysis
	- to find optimal tsr operating range for vawt, usually where cp is highest (cp declines rapidly once tsr surpasses ideal range)
	- they did tsr analysis to find the optimal range, and check that cp was behaving in a normal way and matched literature results
	- can't manually set tsr range in simscale so calculated corresponding angular velocities based on tsr values while maintaining rotor radius and incoming velocity (omega = (TSR\*radius)/Ux)
- transient studies
	- ![[Pasted image 20260714152313.png]]
	- 

## learning w/ wiki 07/15
### pre-run checklist:
- [ ] define study goal
	- rotor design, wind conditions, TSR, output parameters, independent var
- [ ] select physics and time dependency
	- eg incompressible, transient
- [ ] prep geometry
	- prepare CAD, external fluid domain, rotating region
- [ ] define simulation behavior
	- set material, turbulence model, initial conditions, and ALL boundary conditions
- [ ] create and inspect mesh
- [ ] set transient/numerical controls (**Simulation Control**)
	- end time, delta t or adjustable timestep/CFL limit, write interval, runtime limit
- [ ] configure result controls
### set up

before CAD and CFD, identify the following:
- rotor design and variable being studied
- wind conditions (speed, turbulence)
- rotational operating conditions (TSR)
- output parameters (force, moment, flow behavior, etc)
	- esp moment about the rotor axis for turbines!
#### rotational zone
- make a cylinder that completely encompasses the blades, make sure it is a closed volume for proper meshing
- during meshing assign the cylinder volume to a surface refinement and enable **create cell zone**
- assign the cell zone as an MRF or AMI rotating region under **advanced concepts**
#### CAD specs
- solid parts cannot overlap because that can cause geometry operation or meshing failures, all joints must be sharing a face/touching exactly so that no two solids occupy any of the same 3d space
	- strut connections to shaft and blades need to be boolean-unioned which combines them into one body
- use **interference check** in CAD edit and fix any errors with boolean operations or geometry adjustments
	- the automatic *fix interferences* subtracts the smaller body from the larger one so be aware if using it
- tiny unintended gaps can also hurt mesh quality or cause simulation errors

### steady state vs transient
- for vawt: transient lets you see changing blade loads, rotor moment, separation, and wake over time
- steady state solves for a time 
- independent converged solution
	- seeks one flow field that no longer changes with time
	- solves equations without time derivative terms
	- uses SIMPLE pressure-velocity coupling algorithm
	- Delta t is a pseudo time step that controls how aggressively the solver moves through iterations, usually 1 is advisable (that's small)
	- you can inspect residuals and result controls like forces and moments to see if the solution has stabilized
	- can model turbulence and mean wake but cant show variation over time
- transient resolves time dependent behavior
	- advances the solution through simulated time, saves each frame representing a predicted state of the flow at a particular time
	- uses PISO or PIMPLE turbulence-capable pressure-velocity algorithms
	- end time is the total physical duration simulated
	- delta t is the actual time step
		- at each timestep it does sub-iterations and considers the timestep converges when residuals fall below a specified value
	- you can write results every chosen number of timesteps or at selected time intervals
	- CFL / courant number: \[ C = \frac{U \Delta t}{\Delta x} \]
		- compares how far flow information travels during one timestep: U\*delta t, and the size of one mesh cell: delta x (number of cell lengths the flow information crosses per timestep)
		- should use highest local flow speed for U, not necessarily input velocity
		- recommended CFL below 1, often 0.5-0.7 gives good results
			- faster flow increases CFL
			- smaller mesh cells increases CFL
			- lower delta t decreases CFL, adds cost

### mesh stuff
- non orthogonality, lower is better
	- for two neighboring cells, you want the normal vector of their shared face to be perpendicular to a line connecting the center of the cells
	- the angle between the center to center line and the shared face normal is the nonorthogonality, 0 = ideal, 90 = poor
	- CFD computes flux across cell faces so its better if neighboring cell centers align with the face normal so the gradient can be approximated more directly and more accurately
	- high non-orthogonality can slow convergence or cause divergence
	- below 70 is preferred, over 80 you need to improve the mesh, over 85 it will prob diverge
		- 75-82: use one non-orthogonal corrector
		- 82-85: use two, but it would be better to improve the mesh
![[1697359737162.png]]
### results
- result controls - BEFORE the run!!
	- **forces and moments** on rotor surfaces
	- **probe points** in the inflow and wake to track airflow variables over time
	- **field calculations** for diagnostics like vorticity, turbulence quantities, wall shear stress, pressure coefficient
	- **surface data** for averages or integrals over a selected surface
- post processing
	- cutting planes
	- **vectors**
	- particle trances
	- pressure gradients
	- rotational view
- residuals
	- measure used by solver to judge if the current estimate of a variable field (like velocity or pressure) is sufficiently solved
	- residual controls are in the iterative pressure and velocity solver settings
	- low = good, equations are adequately resolved *for the current timestep*
	- stable physical output = good, the thing you're looking at has behaved consistently/repeatably *over the simulated interval*


### simulation control
1. end time: total physical time simulated
2. Delta t: timestep size
3. adjustable timestep / max CFL / max timestep: lets simscale reduce delta t to respect the CFL limit
4. Write interval: how often results are saved
5. Max runtime: caps compute time

for a pilot run prob good to choose adjustable timestep, max CFL = 0.7, conservative max timestep, and write interval enough to resolve the output you need. after the run instpect the timestep and result histories.



## basic flow simulation steps
https://www.youtube.com/watch?v=WsPy_TJotv4 
1. export STEP file from Zoo
2. create a new project in SimScale
	- import geometry
3. edit in CAD mode
	- Flow Volume External (top left)
	- Boolean, subtract (top middle)
		- target body = air
		- tool body = turbine
			- discard tools, apply
	- save as copy (top right)
4. select air, then Create Simulation
	- Incompressible, create
5. Materials, air
6. Boundary conditions
	- air inlet
	- pressure outlet to 0 Pa
	- create wall, select other sides, set velocity to slip
7. Results Control
	- Forces and moments, select all faces of turbine and not air boundary faces
		- select all faces (top right) then deselect boundary faces
		- should have white outlines around turbine and black outlines around air cube
	- maybe set center of rotation
8. Simulation Runs, start
9. Post Process Results
	- click on each boundary face and hide selection to hide air cube
	- default given top view cross section plane, can turn off
	- Part color, pressure shows pressure on turbine
		- can adjust color scale, usually continuous and include upper and lower bounds is good
	- Force Plot, forces and moments plot
		- ignore initial oscillations, values stabilize over time so look at right part of graph
	- Particle trace (top left)
		- position particle trace 1 on inlet boundary by inverting visibility


## wiki notes
### Recommended VAWT CFD workflow
- Define one question first: compare geometry, estimate `Cp`, find a useful TSR range, study wake behavior, or assess a site. CFD is strongest for comparisons and trends, not unvalidated absolute performance. (source: [[CFD and Validation]], [[vj6]], [[vj26]])
- Keep the first CAD model simple: blades, rotor dimensions, shaft, and only major supports or flow modifiers that affect the question (omit stuff like bearings and bolts.
- Learn the workflow with a known airfoil, then validate a published reference VAWT before analyzing the proposed design. (source: [[HRI2526]])
- Use 2D for early airfoil and design screening; use 3D for final performance, blade-tip losses, spanwise flow, support drag, and realistic wake studies. 2D can overpredict `Cp`. (source: [[vj11]], [[vj29]], [[va26]])
- Change one major design variable at a time and keep a case log of geometry, wind speed, TSR, mesh, time step, solver, and results.

### Validation
- Check lift and drag for a known airfoil at a matching Reynolds number and angle of attack.
- Check a reference VAWT against published torque, `Cp`, velocity-field, or wake data.
- Run mesh-independence, time-step-independence, and domain-size-sensitivity studies before trusting performance results. (source: [[va10]], [[va14]], [[va25]])
- Validate more than one `Cp`-versus-TSR curve when possible: compare wake velocity, pressure, separation, vorticity, and blade-tip vortices. PIV or wind-tunnel data are useful targets. (source: [[vj5]], [[vj29]], [[va11]])

### Operating conditions and model choices
- Use incompressible air for ordinary low-speed VAWT cases, set the inlet wind speed and turbulence intensity explicitly, and set the pressure outlet to zero gauge pressure. Match the wind speed and TSR of any validation case. (source: [[HRI2526]], [[vj2]])
- Start with transient URANS and `k-omega SST`, the most common practical design-stage choice. Consider transition SST for low-Reynolds-number transition and separation; use DES or LES only when detailed dynamic stall or vortex fidelity justifies the extra cost. (source: [[vj11]], [[va10]], [[vj5]])
- Use an inner rotating domain and an outer stationary domain. MRF is a cheaper steady approximation; sliding mesh or AMI physically moves the rotating region and is preferable for transient blade-wake interaction, dynamic stall, and fluctuating torque. (source: [[HRI2526]], [[va10]])
- Begin with an outer domain of about `15D` upstream, `10D` downstream, and `20D` laterally, then test whether enlarging it changes torque or `Cp`. Use a larger domain when reproducing an open-field or wind-tunnel condition requires it. (source: [[vj11]], [[va10]], [[va25]])

### Mesh setup
- Refine around blade surfaces, the rotating-domain interface, and the wake. Add boundary-layer layers at the blades and choose near-wall resolution (`y+`) that matches the turbulence-model wall treatment. (source: [[va10]], [[vj6]])
- Increase mesh fineness until torque or `Cp` changes little. Poor or unresolved boundary-layer meshing can make the result unreliable, as the HRI project found. (source: [[HRI2526]], [[va14]], [[va25]])
- Consider running a mesh sensitivity analysis to determine minimum viable mesh size.

### Important limits
- CFD alone cannot reliably establish self-starting, cut-in speed, rooftop performance in multidirectional urban wind, generator losses, or full-scale behavior from a small model. Use site measurements and physical testing where possible. (source: [[HRI2526]], [[va17]], [[va18]], [[vj26]])

Helpful pages: [[CFD and Validation]], [[CFD]], [[Dynamic Stall]], [[Urban Wind Conditions]], [[Wind Tunnel Testing]], [[HRI2526]]
