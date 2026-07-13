## flow simulation basic steps
**note that this example was for a model jet, so some things are not ideal for vawts**
https://www.youtube.com/watch?v=WsPy_TJotv4 
1. export STEP file from Zoo
2. create a new project in SimScale
	- import geometry
3. edit in CAD mode
	- Flow Volume External (top left)
	- Boolean, subtract (top middle)
		- target body = air
		- tool body = turbine
			- discard tool, apply
	- save as copy (top right)
4. delete turbine object from geometries
5. select air, then Create Simulation
	- Incompressible, create
6. Materials, air
7. Boundary conditions
	- air inlet
	- pressure outlet to 0 Pa
	- create wall, select other sides, set velocity to slip
8. Results Control
	- Forces and moments, select all faces of turbine and not air boundary faces
		- select all faces (top right) then deselect boundary faces
		- should have white outlines around turbine and black outlines around air cube
	- maybe set center of rotation
9. Simulation Runs, start
10. Post Process Results
	- click on each boundary face and hide selection to hide air cube
	- default given top view cross section plane, can turn off
	- Part color, pressure shows pressure on turbine
		- can adjust color scale, usually continuous and include upper and lower bounds is good
	- Force Plot, forces and moments plot
		- ignore initial oscillations, values stabilize over time so look at right part of graph
	- Particle trace (top left)
		- position particle trace 1 on inlet boundary by inverting visibility

## HRI2526 lessons learned, set up used
- k-omega SST turbulence model for all studies
- had trouble with boundary layer meshing which significantly decreased the reliability of the cfd
- validated cfd using a naca airfoil and a classical savonius vawt


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
