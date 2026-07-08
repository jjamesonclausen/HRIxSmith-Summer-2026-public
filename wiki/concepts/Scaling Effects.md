---
Created: 2026-06-25
Updated: 2026-07-07
Sources: [[HRI2526]], [[vj11]], [[vj20]]
Source_count: 3
Tags: #concepts
---
## Scaling Effects

Challenges in translating small-scale turbine results to full-scale performance. (source: sources/HRI2526.md)

- Small prototypes do not fully replicate real aerodynamic behavior. (source: sources/HRI2526.md)
- Differences in Reynolds number affect flow characteristics. (source: sources/HRI2526.md)
- Scaling impacts cut-in behavior and tip speed ratio. (source: sources/HRI2526.md)
- The HRI team tested 5 in x 4.5 in prototypes in a 12 in x 12 in wind tunnel, then scaled the selected design toward McConnell Hall rooftop dimensions. (source: sources/HRI2526.md)

The review says laboratory VAWT tests often sit at Re = 10^4-10^5, while real turbines more often run at Re = 10^5-10^6. (source: sources/vj11.md)
It flags laminar separation bubbles and strong Reynolds sensitivity below about 5 x 10^5 as a major reason small-scale results drift from full-scale behavior. (source: sources/vj11.md)
It also notes that the effective Reynolds number changes during a single revolution because relative velocity varies with azimuth. (source: sources/vj11.md)

The vj20 paper gives an explicit similarity workflow: keep blade count, blade profiles, TSR, and material constant while scaling diameter, height, and chord by a common `SL = 11.01`. (source: sources/vj20.md)
It reports derived scaling ratios of `SV = 2.05`, `Somega = 0.301`, and `SP = 4428.49`, then says the scaled-model experimental and CFD results stayed within about `2%-3%` of the full-scale prediction. (source: sources/vj20.md)

Implications:
- Wind tunnel results may not predict rooftop performance accurately. (source: sources/HRI2526.md)
- Requires validation through CFD or full-scale testing. (source: sources/HRI2526.md)
- The report treats scaling as a major uncertainty in translating the low-speed prototype results to real rooftop deployment. (source: sources/HRI2526.md)

Related:
- [[Wind Tunnel Testing]]
- [[CFD]]
- [[Wind Turbine Parameters]]

#concepts 
