# Brainstorming
See [[Design goal]]

## Wind data

https://mesonet.agron.iastate.edu/request/asos/1min.phtml

collected at 9m from ground

Avg wind speed: 4.8 m/s
Avg gusts: 6.3 m/s

Figure 1: Histogram of hourly wind speed from Jul 2025 - July 2026. There are significant gaps so only about 73% of the year is represented. For AEO calculations we will use a 5 year span.

![[BOS_07.25_to_07.26_histogram.svg]]

Figure 2: Histogram of hourly wind speed from Jul 2021 - Jul 2026. This is the five-year BOS distribution intended for AEO-oriented analysis.

![[BOS_07.21_to_07.26_histogram.svg]]


## Design thoughts

- Most Darrieus turbines have rated speed around 10-15 m/s and cut-out speed around 20 m/s according to the LLM wiki
- Va9 EN0005 Darrieus turbine has a cut in speed < 2 m/s!
- should design turbine to be at a similar height as wind measurements for best estimations of power production. (Wind speed can vary dramatically in the turbulent boundary layer near the ground.)
- 

## Anna 
### Design Criteria 
- competitive efficiency compared to current on-the-market vawts
- designed for optimal performance at installation site (better than avg vawt for BOS)
  - able to cut in to optimize use of available wind energy
- should be reasonable to manufacture, not more complex than necessary
- minimal maintenance requirements

- economic feasibility
  - should produce enough power to offset its cost within half its lifetime
- must comply with airport regulations
  - no structure can intercept an imaginary space, see concepts/airport regulations 

- should be reasonable to model in Zoo*
- compatible with good CFD practices*
\*within our timeline
#### Wind
Avg speed: 4.8 m/s
Avg gusts: 6.3 m/s

### Design Concepts 
#### Criteria:
- start up ability, ideally <= 3 m/s 
- good enough efficiency to be economic
- rated speed ~ 10 m/s
- cut-out speed >= 20 m/s
- room for growth (are there parameters that seem promising which we can plausibly model)
- CADing ability + manufacturability
- interesting to us

#### Classic concpets
- **straight blade, H type Darrieus**
	- easy to model and adjust
	- good efficiency
	- prioritize start up ability with blade profile and geometry! see EN0005
		- [[Airfoil Selection for Small Straight-Bladed VAWTs]]
	- [[va9 EN0005 Self-start Darrieus VAWT]]
		- cut in w Cp 0.416 at 1.25 m/s
		- positive start torque
	- [[va25]] and [[va26]] have validated h type cfd studies
	- can try adjusting pitch (fixed), [[va26]]
- **helical Darrieus**
	- smoother torque, lower cyclic loading = easier on generator and mech parts = less maintenance/longer life
	- [[va22 100-W Helical-Blade Vertical-Axis Wind Turbine]]
		- low TSR = quiet, but we don't need that and usually darrieus rotors are more efficient at higher tsr
		- 3.5 m/s cut in
		- 114.7 W at 9 m/s
- **hybrid/multi-rotor option**
	- start up help, but still good efficiency
	- avoid inner savonius layout bc interference
	- [[vj2]] moved sav blades outside darr core and increased torque
	- [[vj20]] has cp = 0.486 and good self start w/ inner/outer dual h rotor 
		- intriguing bc  simple design = good CAD/manufacturability
#### Alternate picks (unique)
- [[va20 Involute Blade Type Rotor]] lift based w/ some drag help
- [[va20 Involute Rotor with Wind Flow Modifier]]  
	- Cp 0.22 at 5 m/s for involute rotor alone
	- cp 0.397 at 5 m/s w added wind flow modifier
	- no strong experimental validation but good CFD results
	- would need circular or semicircular WFM to cover at least the directions wind most frequently comes from
- [[vj20 Proposed Hybrid VAWT]]
	- inner asymmetric airfoil H rotor hybrid
	- cp 0.486 at tsr 3
	- self starting
	- 11-13% better than standard h rotor and cited hybrids
	- complex
- [[va23 Shifted Troposkien Vertical Offset]]
	- 50% shift performed very well
- [[vj9 Scooplet-Based Savonius]]
	- 39% increased cp compared to classical savonius
	- simple, manufacturable geometry
	- lower efficiency ceiling than lift based
