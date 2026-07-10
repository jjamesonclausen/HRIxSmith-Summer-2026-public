# j710 va9 initial

## Goal

Create a first-pass CAD handoff note for `[[va9 EN0005 Self-start Darrieus VAWT]]` that can be pasted into an AI 3D modeling tool.

## Best Reference Files

- `attachments/images/va9-fig26.jpg`
  - Prototype photo. (source: `sources/va9.md`)
- `attachments/images/va9-fig23.jpg`
  - Blade-end configuration drawing. (source: `sources/va9.md`)
- `attachments/images/va9-fig5.jpg`
  - EN0005 blade profile figure. (source: `sources/va9.md`)

## Source-Backed Dimensions

- Blade body height: `36.0 cm` (source: `sources/va9.md`)
- Total rotor height: `48.0 cm` (source: `sources/va9.md`)
- Rotor radius: `17.3 cm` (source: `sources/va9.md`)
- Blade profile chord: `5.3 cm` (source: `sources/va9.md`)

## Source-Backed Geometry Rules

- The blade is made of `3` parts: one main body plus two blade ends. (source: `sources/va9.md`)
- The blade ends can be placed toward the inside, toward the outside, or parallel to the main blade body. (source: `sources/va9.md`)
- Inward-positioned blade ends are reported to increase drag at standstill and improve self-start capability. (source: `sources/va9.md`)
- The EN0005 blade profile is described as:
  - upper surface: high-lift
  - first `20%` of lower surface: high-lift
  - remaining lower surface: cup form
  (source: `sources/va9.md`)

## CAD Prompt

```text
Create a 3D CAD model of the VA9 EN0005 self-start Darrieus VAWT using the attached reference images.

Goal:
Model the external rotor geometry as closely as possible to the published VA9 prototype. Prioritize overall shape accuracy, blade-end geometry, and clean parametric structure over tiny hardware details.

Use these source-backed dimensions:
- Blade body height: 36.0 cm
- Total rotor height: 48.0 cm
- Rotor radius: 17.3 cm
- Blade profile chord: 5.3 cm

Use these source-backed geometric rules:
- This turbine uses blades made of 3 parts: 1 main body plus 2 blade ends.
- The blade ends are angled relative to the main body.
- Model the blade-end configuration like the inward-angled configuration shown in Fig. 23B / the prototype photo, because the source says inward-positioned blade ends increase drag at standstill and improve self-starting.
- The blade ends should look like lift-capable extensions of the main blade body, not separate flat tabs.
- The rotor should match the prototype's overall proportions and silhouette from the reference photo.

Blade profile guidance:
- Use the EN0005 blade profile idea described in the source:
  - upper surface is a high-lift surface
  - the first 20 percent of the lower surface is also high-lift
  - the remaining lower surface finishes in a cup form
- If exact EN0005 coordinates cannot be reconstructed from the reference image, create the closest smooth parametric approximation possible and clearly label it as an approximation.

Modeling instructions:
- Build the model as a parametric assembly or parametric part set.
- Keep these parameters editable:
  - rotor radius
  - total rotor height
  - blade body height
  - chord
  - blade-end angle
  - blade-end length
  - blade count
- Create the main vertical shaft, upper and lower supports, and blades.
- Keep support-arm geometry simple but visually close to the prototype.
- Focus on the aerodynamic rotor shape first; small fasteners, electronics, and sensor hardware can be omitted.
- Use symmetry/patterns where appropriate.

Important constraints:
- Do not invent hidden dimensions as fixed facts.
- Where dimensions are missing, infer proportions from the images and flag each inferred value.
- If blade count cannot be determined confidently from the references, stop and ask for confirmation instead of guessing.
- Name all inferred parameters clearly.

Deliverables:
1. A clean 3D model of the turbine
2. A list of exact source-backed dimensions used
3. A separate list of inferred dimensions/choices
4. A short note describing any assumptions made about:
   - blade count
   - blade-end angle
   - support-arm geometry
   - EN0005 profile reconstruction
```

## What Is Definitely Grounded

- `36.0 cm` blade body height (source: `sources/va9.md`)
- `48.0 cm` rotor height (source: `sources/va9.md`)
- `17.3 cm` rotor radius (source: `sources/va9.md`)
- `5.3 cm` chord (source: `sources/va9.md`)
- blade = main body + two blade ends (source: `sources/va9.md`)
- blade ends can be angled inward, outward, or parallel (source: `sources/va9.md`)
- inward blade ends improve self-start through added drag at standstill (source: `sources/va9.md`)
- EN0005 lower surface ends in a cup form (source: `sources/va9.md`)

## Still Uncertain

- The repo does not currently give a clean coordinate table for the full EN0005 airfoil.
- The repo does not currently give every hidden structural dimension.
- The note should treat support-arm geometry and exact blade-end angle as inferred unless another source is added.

## Related

- [[va9 EN0005 Self-start Darrieus VAWT]]
- [[H-VAWT]]
- [[Straight-bladed Darrieus]]
