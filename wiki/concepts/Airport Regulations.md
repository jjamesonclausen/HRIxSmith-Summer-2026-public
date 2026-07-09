---
Created: 2026-07-09
Updated: 2026-07-09
Sources:
  - "[[active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace]]"
  - "[[active/analysis/Design goal.pdf|Design goal]]"
Source_count: 2
tags:
  - concepts
---
## Airport Regulations

This page covers the airport-airspace constraints that matter when screening VAWT placement near runways and terminals at Boston Logan International Airport. (source: active/analysis/Design goal.pdf, active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)

- The Logan design brief explicitly identifies two siting questions: whether turbines could be placed near runway areas, including the field around the weather station, and whether turbines could be placed on terminal roofs without conflicting with airspace. (source: active/analysis/Design goal.pdf)
- Part 77 requires FAA notice for construction or alteration above `200 ft` AGL, and also for shorter structures that penetrate the applicable airport imaginary surfaces. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- For public-use airports and airports with FAA-approved instrument approaches, the relevant civil airport imaginary surfaces are the horizontal, conical, primary, approach, and transitional surfaces. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- The horizontal surface is a plane `150 ft` above established airport elevation, with `10,000 ft` arcs for non-utility runways. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- The primary surface is centered on the runway and extends `200 ft` beyond each end for hard-surface runways. Its width is up to `1,000 ft` for precision and certain non-precision instrument runways. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- Approach surfaces extend outward from runway ends. Their slope can be `20:1`, `34:1`, or `50:1` depending on runway type and approach category, and precision-runway approach surfaces can continue beyond the first `10,000 ft` at `40:1`. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- Transitional surfaces extend outward and upward from the sides of the primary and approach surfaces at a slope of `7:1`. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- Part 77 also treats any object that exceeds an airport imaginary surface as an obstruction standard trigger, even when the structure is well below `200 ft` AGL. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- The regulation separately exempts certain meteorological devices meeting FAA-approved siting criteria, but that exemption is specific to those devices and does not itself approve a turbine at the same location. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)

## Logan screening implications

> Inference: The statements in this section are site-screening interpretations of Part 77 applied to the Logan design brief. The repo does not currently include a Logan Part 77 map, terminal roof elevations, or runway-by-runway approach classifications.

- The most constrained locations are likely the spaces between runways and the areas directly off runway ends, because those locations are governed by the primary, transitional, and approach surfaces. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md, active/analysis/Design goal.pdf)
- Side-perimeter locations along the runway complex are more plausible screening candidates than end-of-runway locations, because the transitional surface opens upward at `7:1` away from the runway-side boundaries. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- A `30 ft` ground-mounted turbine would need about `210 ft` of horizontal separation from the relevant primary or approach-surface edge to fit below a `7:1` transitional surface, before considering any stricter local condition. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- A `30 ft` structure under an approach surface would need about `600 ft` of horizontal distance at `20:1`, about `1,020 ft` at `34:1`, or about `1,500 ft` at `50:1` to remain below that surface. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- Because of that geometry, a `30 ft` turbine is more plausible near outer side-perimeter areas than in fields between runways or directly beyond runway thresholds. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md, active/analysis/Design goal.pdf)
- Rooftop turbines may be possible only where the roof plus turbine height stays below the controlling surface. If a roof is only under the horizontal surface, the top of the turbine must stay at or below `150 ft` above established airport elevation. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- The allowed turbine height above a roof is therefore the remaining vertical distance between the roof elevation and the applicable Part 77 surface, not one fixed airport-wide rooftop limit. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)

## Practical use in this project

- Part 77 is a screening tool for this project, not a final siting approval. (source: active/resources/14 CFR Part 77 -- Safe, Efficient Use, and Preservation of the Navigable Airspace.md)
- For Logan, the next data needed to turn this screening into a real siting answer are a runway-by-runway airport layout, terminal roof elevations, and a point-by-point obstruction review for candidate sites. (source: active/analysis/Design goal.pdf)
- The current project brief already frames a fallback option: if the preferred runway-area or rooftop locations are too constrained, the team may need a nearby airport-adjacent site with similar wind conditions around `9 m` above ground. (source: active/analysis/Design goal.pdf)

Related:
- [[Urban Wind Conditions]]
- [[Economic Viability of VAWTs]]
- [[Architectural Wind Turbines]]
- [[CFD and Validation]]

#concepts
