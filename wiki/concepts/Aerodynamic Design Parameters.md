---
Created:
Updated: 2026-07-02
Sources:
- [[sources/HRI2526.md]]
- [[sources/va8.md]]
- [[sources/vj1.md]]
- [[sources/vj11.md]]
- [[sources/vj4.md]]
- [[sources/vj8.md]]
Source_count: 6
Tags:
- concepts
---
## Aerodynamic Design Parameters

These are the main geometry knobs the sources repeatedly treat as design variables.

- Tip Speed Ratio (TSR) is one of the core performance controls. (source: sources/HRI2526.md, sources/vj1.md)
- Blade pitch angle is a major tuning variable. (source: sources/vj8.md)
- Relative airfoil thickness affects performance and should be checked alongside pitch. (source: sources/vj8.md)
- Rotor spacing matters in contra-rotating arrangements. (source: sources/vj8.md)
- Included angle is another tuning variable in the contra-rotating study. (source: sources/vj8.md)
- Blade number, camber line, and blade inclination are key architectural choices for small VAWTs. (source: sources/vj4.md)
- Solidity changes the balance between efficiency and starting behavior. (source: sources/vj1.md, sources/HRI2526.md)
- Swept area, Reynolds number, and starting torque remain basic sizing parameters. (source: sources/HRI2526.md, sources/vj6.md)
- The VAWT review gives Savonius TSR around 0.6-1.2, Darrieus TSR around 2.5-5.0, and emphasizes that the optimum shifts with solidity. (source: sources/vj11.md)
- It treats blade profile, pitch angle, blade count, and chord Reynolds number as the main coupled design knobs. (source: sources/vj11.md)
- It notes that low-solidity rotors push peak Cp to higher TSR, while high-solidity rotors self-start better but suffer more blade-wake interaction. (source: sources/vj11.md)
- The va8 patent treats asymmetrical blade profile geometry as a startup-torque design knob, specifying upper/lower surface path difference of 20% of chord, chord-line-to-bottom-surface path difference of 3% of chord, and maximum-thickness-to-chord ratio of 11.5%. (source: sources/va8.md)
- The same patent fixes the angle between blade chord line and horizontal beam at 25 degrees, and its wind tunnel observations show maximum lift coefficient near a 25-degree angle of attack for the tested profile. (source: sources/va8.md)

![Figure 4: asymmetrical blade profile and chord/camber definitions in the va8 patent](../../images/va8-fig4.jpg)
![Figure 5: va8 wind tunnel lift-coefficient curves versus angle of attack](../../images/va8-fig5.jpg)

Related:
- [[Wind Turbine Parameters]]
- [[Rules of Thumb]]
- [[Wind Tunnel Testing]]
