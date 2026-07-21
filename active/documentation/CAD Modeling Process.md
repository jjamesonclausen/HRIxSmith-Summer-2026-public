# CAD Modeling Process

## Purpose and Scope

This document records the CAD work undertaken for the VAWT project: translating research into AI-CAD prompts, constructing and refining candidate turbine geometries, and preparing models that could eventually support CFD. It combines the CAD-log record with Julie's related daily-log notes. It describes the recorded process and tool outputs; it does not establish that any model is physically manufacturable, aerodynamically accurate, or CFD-validated. (source: active/documentation/CAD log; source: active/_Julie_daily_log.md)

## Process Overview

The CAD workflow followed five recurring steps:

1. Extract source-backed geometry and distinguish it from missing dimensions.
2. Write a constrained prompt that keeps the known geometry fixed and requires inferred hardware to be named as an assumption.
3. Generate a parametric model in ZooKeeper/KCL or Fusion.
4. Inspect rendered geometry, identify visible or structural problems, and make focused edits.
5. Check that the CAD tool reports successful execution and constrained sketches, while treating those software checks as distinct from engineering validation.

This process developed alongside the research wiki. Julie recorded that the team selected two designs to explore, tracked prompts for ZooKeeper, exported conversations into the CAD log, and began an initial ZooKeeper model. (2026-07-10; source: active/_Julie_daily_log.md)

## VA9 EN0005 Self-Start Darrieus Model

### Starting from the source

The VA9 work began as a first-pass AI-CAD handoff based on the published prototype. The source-backed geometry provided a `36.0 cm` blade-body height, `48.0 cm` total rotor height, `17.3 cm` rotor radius, and `5.3 cm` blade-profile chord. Each blade was defined as a main body plus two blade ends. Inward-positioned blade ends were selected because the source reports that they increase standstill drag and improve self-starting. (source: active/documentation/CAD log/j710_va9_initial.md)

The prompt required an editable parametric assembly, with rotor radius, height, blade-body height, chord, blade-end angle, blade-end length, and blade count available for later adjustment. It also required any unknown dimensions, including support geometry and exact EN0005 reconstruction, to be clearly identified as inferred rather than presented as source facts. (source: active/documentation/CAD log/j710_va9_initial.md)

### Initial ZooKeeper/KCL assembly

ZooKeeper created a multi-file KCL model with separate parameter, blade-body, blade-end, support-arm, shaft/support, and assembly files. The recorded model used a three-blade assembly, a central shaft, upper and lower supports, and inward-angled blade ends. The exact EN0005 coordinates were unavailable, so the blade profile was explicitly modeled as an editable approximation rather than an exact reconstruction. (source: active/documentation/CAD log/4eed3e3d-51dc-43a6-8dc7-1b7ae205f045.md)

The tool reported constraint, lint, execution, bounding-box, and rendered-view checks. It also identified limitations: the airfoil-like profile was faceted, the exact profile coordinates were unavailable, and several structural dimensions and blade-end parameters were inferred. The extended shaft was intentionally outside the `480 mm` rotor envelope to resemble the prototype mast. (source: active/documentation/CAD log/4eed3e3d-51dc-43a6-8dc7-1b7ae205f045.md)

### Blade-end refinement cycle

Most of the VA9 modeling work became a detailed iteration on the blade ends. The documented goals were to make the ends align to the main blade, point inward at the desired angle, retain a cup-like EN0005-inspired profile, and form a smooth transition rather than looking like separate tabs. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)

Key iterations included:

- Replaced the original rotated-extrusion and trim approach with lofted blade-end caps whose root profiles match the main-blade tips. This was done after an exact alignment adjustment made the trim boolean unstable. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Increased the inward rake to `48 deg`, then later changed it to `58 deg` to create a flatter, more inward appearance, and finally set it to `46 deg`. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Added near-root and intermediate loft profiles to smooth the blade-body/end transition, then changed the loft from cubic to quadratic after the middle section appeared to dip inward. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Added a root-ease profile and attempted a union of the blade body and both ends so each blade would behave as a more continuous body. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Increased the cup depth and later documented a specific cup-depth parameter so the profile could be adjusted manually. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Tested a wider outer lip while holding the root/inner connection fixed, then reverted that change when it was not desired. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- Increased the blade-end trace from `9` to `18` constrained segments and revised both the blade-body and blade-end profiles to approximate the supplied VA9 Figure 5 profile more closely. The recorded final refinement retained the `46 deg` inward rake and smooth loft transition. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)

### Current recorded VA9 limitations

The denser blade-end trace caused the KCL engine's three-body boolean union to fail. The recorded fallback was to leave the blade body and blade ends as aligned, touching bodies rather than a fused solid. This means the model may render as connected but is not currently one boolean-joined blade body. (source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)

The final profile is an approximation digitized from a figure, not an exact EN0005 coordinate set. More source coordinates, a successful robust union, and independent geometry inspection would be needed before treating this as a final production or simulation model. (source: active/documentation/CAD log/j710_va9_initial.md; source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)

## VJ20 Dual-H-Rotor Hybrid Model

### Model definition

The `vj20` concept was modeled as a concentric dual-H-rotor VAWT: an outer three-blade NACA0018 H-rotor and an inner three-blade DU 06-W-200 H-rotor on a shared shaft. The inner rotor is offset by `60 deg`, and each three-blade rotor is spaced at `120 deg`. The CAD note separated source-backed rotor dimensions from inferred support hardware. (source: active/documentation/CAD log/a_vj20.md)

The prompt explicitly prohibited adding a Savonius rotor, helicity, taper, variable pitch, shrouds, or guide vanes. It requested straight, constant-chord airfoil blades and required inferred shafts, hubs, struts, bearings, and mounting geometry to remain clearly labeled. (source: active/documentation/CAD log/a_vj20.md)

### ZooKeeper attempt and repair lessons

The initial ZooKeeper result reported source dimensions, fully constrained sketches, and successful execution. However, the visual review found disconnected blades. Later joint-refinement work added a shared rotating assembly, stationary assembly, `rotorAzimuth` parameter, split bearing concepts, hub bores, struts, and fixed-pitch blade brackets. (source: active/documentation/CAD log/a_vj20.md)

Visual inspection remained essential. After a repair, the log records floating blocks around inner blades; after those blocks were removed, an inner top strut was missing; the next stated repair still did not correct the issue and the inner blade brackets appeared incorrect. These outcomes show why a passing execution check was not enough to accept the model. (source: active/documentation/CAD log/a_vj20.md)

### Fusion comparison

The same shorter, production-oriented prompt was tried in Fusion. The log records a fast, visually strong dual-H-rotor model with both full-scale and scaled-down configurations. However, on closer inspection, the inner blades did not use the correct asymmetric airfoil shape. (source: active/documentation/CAD log/a_vj20.md)

Julie also recorded that Fusion's AI tools seemed faster than ZooKeeper, while later experiencing performance slowdowns. She recorded that Anna created CAD in Fusion for a subsequent simulation attempt. (2026-07-20; source: active/_Julie_daily_log.md)

The recorded conclusion is therefore limited: Fusion produced a promising visual starting point quickly, but the actual airfoil geometry still needed verification before it could be used as a faithful `vj20` model. (source: active/documentation/CAD log/a_vj20.md)

## Savonius Benchmark Geometry

The CAD log also includes a separate prompt for a classical two-bucket Savonius rotor intended as a CFD-validation benchmark. Its purpose was intentionally narrower than the VA9 and `vj20` models: recreate only the aerodynamic bucket layout from the available source information, keep the buckets as separate bodies, and exclude shaft, hub, endplate, support, wall-thickness, and manufacturing details that were not supported by the sources. (source: active/documentation/CAD log/a716_va29_sav.md)

The log explicitly warns that the available papers do not contain enough exact geometry or setup information to recreate a classical validation rotor reliably. Any resulting model must be treated as an assumed geometry and must agree with experimental reference data before being called validated. (source: active/documentation/CAD log/a716_va29_sav.md)

## Connection to CFD Preparation

CAD and CFD development overlapped. Julie used simple ZooKeeper geometries to learn SimScale, ran a practice simulation on a random airfoil, copied an airfoil for further work, and later worked through NACA0018 and NACA0012 airfoil cases. (2026-07-13 to 2026-07-16; source: active/_Julie_daily_log.md)

The `vj20` CAD log distinguished a mechanical/joint-correct assembly from a CFD-clean model. For a future CFD-ready model, it proposed a shared rotating group for blades, struts, hubs, and shaft; a stationary group for bearing housings and generator support; an adjustable rotor azimuth; a rotating zone; a far-field domain; and named surfaces. These are documented design recommendations, not evidence that a complete CFD-ready `vj20` model was produced. (source: active/documentation/CAD log/a_vj20.md)

## Lessons From the CAD Process

- Source-backed geometry and inferred geometry must remain separate. Exact rotor dimensions can be preserved while support hardware and hidden dimensions stay editable assumptions. (source: active/documentation/CAD log/a_vj20.md; source: active/documentation/CAD log/j710_va9_initial.md)
- Shorter, constrained prompts can produce clearer first-pass outputs than long prompts, but visual and geometric review is still necessary. The CAD log explicitly notes a better initial ZooKeeper result from a less overwhelming prompt. (source: active/documentation/CAD log/a_vj20.md)
- Software reports that sketches are constrained or code executes do not guarantee that geometry is visually correct, mechanically coherent, or source-faithful. Disconnected blades, floating brackets, missing struts, incorrect airfoils, and boolean-engine failures were all found through later inspection. (source: active/documentation/CAD log/a_vj20.md; source: active/documentation/CAD log/b46becaa-ac7e-4343-91b5-307ebca919dc.md)
- AI-CAD is useful for fast iteration, but Julie was concerned that rapidly generated geometry might lack a stable underlying structure for future edits. She also found it important to know which code lines changed so manual adjustment remained possible. (2026-07-10; source: active/_Julie_daily_log.md)
- The project treats the CAD workflow as part of learning how to use AI intentionally. The tools can speed exploration, but the team still needs to understand the source geometry, inspect each revision, and validate any model before relying on it. (2026-07-10; 2026-07-15; source: active/_Julie_daily_log.md)

## Open Work

1. Obtain or digitize authoritative EN0005 coordinates if a higher-fidelity VA9 section is required.
2. Decide whether the VA9 blade should remain a multi-body representation or be reworked into a robust fused solid without losing its dense profile trace.
3. Correct and independently check the `vj20` inner asymmetric airfoil before using the Fusion model as a source-faithful geometry.
4. Build a simplified, watertight CFD variant only after selecting the geometry to validate and defining the necessary rotating and stationary regions.
5. Validate any CAD-derived CFD result against appropriate experimental or published reference data before drawing aerodynamic conclusions.
