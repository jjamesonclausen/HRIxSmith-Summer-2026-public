# VAWT Basics

This is a living learning note for designing a vertical-axis wind turbine (VAWT). Add later lessons below the `Future Lessons` heading.

## Core Idea

Separate VAWT design into two kinds of things:

- **Performance variables** are the results you measure to judge the turbine.
- **Design choices** are the geometry or system decisions you change to influence those results.

No single metric defines a good VAWT. The sources frame useful design as a tradeoff among startup, efficiency, torque ripple, loading, durability, and site conditions. (source: sources/vj11.md, sources/vj18.md)

## Performance Variables

| Variable | Meaning | Why it matters |
| --- | --- | --- |
| Coefficient of power (`Cp`) | Fraction of available wind power extracted by the rotor | Main aerodynamic-efficiency metric. Compare it at the stated wind speed and TSR, not by itself. (source: sources/HRI2526.md, sources/vj11.md) |
| Starting torque | Torque available before the rotor rotates | It must exceed friction and inertia for the rotor to self-start. (source: sources/HRI2526.md) |
| Cut-in speed | Wind speed where the turbine begins rotating | Lower values are important at low-wind sites. (source: sources/HRI2526.md) |
| Rated speed | Wind speed where rated power is achieved | It should fit the useful wind-speed range at the intended site. (source: sources/HRI2526.md) |
| Rated power | Maximum intended power output | It is not enough on its own if the site rarely reaches rated wind speed. (source: sources/HRI2526.md) |
| Cut-out speed | Wind speed where the turbine shuts down to prevent damage | It indicates the high-wind operating limit. (source: sources/HRI2526.md) |
| Tip-speed ratio (`TSR`) | Ratio of blade-tip speed to wind speed | Each rotor has an efficient operating range. (source: sources/HRI2526.md, sources/vj11.md) |
| Torque ripple | Torque variation through a rotation | High ripple means pulsating loads, vibration, and more difficult mechanical design. (source: sources/vj11.md) |
| Capacity factor | Actual energy generated divided by theoretical maximum energy | It is useful for judging annual energy value, not only peak output. (source: sources/vj14.md) |
| Reynolds number | Flow-regime indicator around the blade | It affects whether an airfoil behaves as expected at the turbine's size and wind speed. (source: sources/vj28.md) |

## VAWT Families

| Family | Typical strength | Typical limitation |
| --- | --- | --- |
| Savonius / drag rotor | Strong self-starting and low-speed torque | Lower peak efficiency. (source: sources/vj11.md) |
| Darrieus / lift rotor | Higher peak `Cp` potential | Poorer self-starting behavior. (source: sources/vj11.md) |
| Hybrid | Uses a drag-oriented element for startup and a lift-oriented element for higher-speed performance | More aerodynamic and structural complexity. (source: sources/vj2.md, sources/vj20.md, sources/vj11.md) |

The review gives typical TSR ranges of `0.6-1.2` for Savonius and `2.5-5.0` for Darrieus, with typical peak `Cp` ranges of `0.15-0.25` and `0.35-0.45`, respectively. These are review-level ranges, not guaranteed values for every turbine. (source: sources/vj11.md)

## Main Design Choices

| Design choice | Mainly affects | Important tradeoff |
| --- | --- | --- |
| Blade profile / airfoil shape | `Cp`, startup torque, stall behavior | A startup-oriented profile can reduce higher-TSR performance. (source: sources/va15.md, sources/va25.md, sources/vj28.md) |
| Blade count | Torque smoothness, startup, solidity | More blades can improve low-wind torque but may reduce peak efficiency. (source: sources/vj22.md, sources/vj21.md) |
| Solidity | Startup torque, optimum TSR, peak `Cp` | Higher solidity helps self-start but usually lowers peak power and narrows the efficient TSR range. (source: sources/va15.md, sources/vj21.md, sources/vj11.md) |
| Chord length / chord-radius ratio | Solidity, Reynolds number, flow curvature | Excessively large chord relative to radius tends to hurt aerodynamic efficiency. (source: sources/vj21.md) |
| Rotor height and radius | Swept area, power potential, structural loads | Larger swept area captures more wind but raises structural and manufacturing demands. (source: sources/HRI2526.md, sources/vj25.md) |
| Aspect ratio (`H/R`) | `Cp`, RPM, Reynolds number, inertia | Lower aspect ratio raised Reynolds number and slightly raised `Cp` in one H-rotor study, but also lowered RPM and increased inertia. (source: sources/vj25.md) |
| Fixed blade pitch | `Cp`, torque, stall | Small changes can help; excessive positive or negative pitch can increase separation losses. (source: sources/va26.md) |
| Variable pitch | Startup, `Cp`, load control | It can improve performance but adds actuators, joints, maintenance, and modeling complexity. (source: sources/va24.md, sources/vj18.md) |
| Helical twist | Torque ripple, noise, cyclic loading | It can smooth loads but may lower peak power and complicate manufacturing. (source: sources/va7.md, sources/vj11.md) |
| Blade-end geometry | Startup and rotational stability | The `va9` EN0005 uses angled blade ends to improve startup behavior. (source: sources/va9.md) |
| Deflectors / flow modifiers | Local flow speed, torque, `Cp` | They can improve flow but may be directional and add structure. (source: sources/vj27.md, sources/va20.md) |
| Hybrid drag + lift layout | Startup and high-speed efficiency | It can combine strengths of both families but increases interference and complexity. (source: sources/vj2.md, sources/vj20.md, sources/vj11.md) |

## The Central Tradeoff

For a Darrieus or H-rotor:

- Low solidity, fewer blades, and lift-focused geometry often favor higher peak `Cp`.
- Higher solidity, more blades, drag assistance, or startup-oriented blade geometry often favor startup torque.

You usually cannot maximize both startup and peak efficiency at the same time. (source: sources/va15.md, sources/vj11.md, sources/vj21.md)

## Example: VA9 EN0005

The `va9` EN0005 design is an example of intentionally trading a plain blade shape for stronger startup behavior.

- Its blade profile has a high-lift upper surface, a high-lift first `20%` of its lower surface, and a lower surface that finishes in a cup form. (source: sources/va9.md)
- The cup form is intended to add helpful drag while stopped, then contribute negligible drag after rotation begins. (source: sources/va9.md)
- Each blade has a main body plus two blade ends; inward-positioned blade ends are reported to increase standstill drag and improve self-starting. (source: sources/va9.md)
- Field tests report self-starting at `1.25 m/s`, `Cp = 0.416` at that wind speed, and stable behavior in a `25 m/s` wind-tunnel stress test. (source: sources/va9.md)

> Uncertainty: the repo does not include a clean coordinate table for the full EN0005 airfoil or every blade-end dimension. (source: sources/va9.md)

## First Design Workflow

1. Define the site and wind regime. (source: sources/HRI2526.md, sources/vj3.md)
2. Choose a turbine family that fits the use case. (source: sources/vj1.md, sources/vj2.md, sources/vj4.md, sources/vj8.md)
3. Set first-pass targets for cut-in speed, rated speed, `Cp`, cut-out speed, and swept area. (source: sources/HRI2526.md, sources/vj1.md)
4. Select a simple baseline geometry.
5. Change one major parameter at a time, such as blade count, airfoil, solidity, pitch, or aspect ratio. (source: sources/vj11.md, sources/vj21.md)
6. Compare `Cp`, starting torque, torque ripple, loads, and site fit instead of only one result. (source: sources/vj11.md, sources/vj18.md)
7. Validate the model with CFD and, if possible, experiments. (source: sources/vj5.md, sources/vj6.md)

## BOS Reminder

The current BOS notes give average wind around `4.8 m/s` and average gusts around `6.3 m/s`. That makes low-speed startup and useful low-wind operation especially important; high peak `Cp` alone is not enough. (source: active/analysis/brainstorm.md)

## How To Get Performance Data

CAD gives you the turbine's geometry. It does **not** by itself give you `Cp`, torque, loads, or cut-in speed. Those values must come from a performance model, CFD, a physical test, or a combination of those methods. (source: sources/vj2.md, sources/vj5.md, sources/vj6.md)

### Three Practical Methods

| Method | What you provide | What you can get | Best use | Main limitation |
| --- | --- | --- | --- | --- |
| Rotor-performance model | Geometry, airfoil data, wind speed, TSR or RPM | Estimated `Cp` versus TSR, power versus wind speed, and comparative blade-count or airfoil trends | Fast first-pass screening | Not sufficient as final proof of full-turbine performance. (source: sources/vj22.md) |
| CFD | CAD geometry, air properties, wind speed, RPM/TSR, domain, mesh, and turbulence model | Torque, `Cp`, pressure, forces/loads, separation, and wake behavior | Comparing selected geometry changes in detail | Results depend strongly on setup; early `2D` CFD can overpredict absolute `Cp`. (source: sources/vj6.md, sources/vj11.md, sources/vj29.md) |
| Physical test | Prototype, controlled wind, and sensors | Actual startup, RPM, torque, power, voltage/current, and measured `Cp` | Validating the model and checking real startup | Scale effects and wind-tunnel blockage can distort the result. (source: sources/HRI2526.md, sources/va15.md, sources/va23.md) |

### A Good Beginner-to-Expert Workflow

1. **Make the CAD geometry.** Define blade count, radius, height, chord, airfoil, pitch, and support geometry. These are your inputs, not your results. (source: sources/vj21.md, sources/vj25.md)
2. **Use a fast screening tool or streamtube model.** QBlade was used in one source to compare airfoils and blade counts, producing `Cp` versus TSR and power versus wind-speed curves. (source: sources/vj22.md)
3. **Choose a few promising versions.** Do not run expensive CFD for every possible geometry. The sources describe optimization workflows that use lower-cost models or surrogate methods to reduce direct CFD calls. (source: sources/va2.md, sources/vj17.md)
4. **Run transient rotor CFD on those few versions.** CFD can estimate torque, `Cp`, blade forces, separation, and wake behavior. (source: sources/vj2.md, sources/vj5.md, sources/vj6.md)
5. **Build and test the best candidate.** Measure actual cut-in, RPM, torque, and electrical output; use the result to check whether the model is believable. (source: sources/va15.md, sources/vj20.md, sources/va21.md)

### What To Request From Each CFD Run

For every version of your design, keep wind speed, rotational condition, and all unchanged geometry the same. Change only the parameter you are studying.

Request these outputs:

- Average torque and torque versus rotor angle
- `Cp` versus TSR
- Power versus wind speed
- Blade pressure and aerodynamic force history
- Evidence of flow separation and dynamic stall
- Wake velocity and turbulence behind the rotor

Torque, `Cp`, flow separation, and wake dynamics are specifically identified as core VAWT CFD outputs in the reviews. (source: sources/vj6.md)

### How To Get Each Variable

| Variable | Simulation or test method |
| --- | --- |
| `Cp` | Run the rotor at several TSR values and make a `Cp` versus TSR curve. Streamtube models and CFD can estimate it; experiments can measure and validate it. (source: sources/va9.md, sources/vj22.md, sources/va25.md) |
| Torque | CFD integrates aerodynamic blade forces into rotor torque; physical tests can measure force with a dynamometer and convert it to torque. (source: sources/vj2.md, sources/vj20.md) |
| Startup / cut-in | Start from rest or very low RPM and increase wind speed until the rotor reaches constant rotation. This is harder to predict reliably than steady running. (source: sources/HRI2526.md, sources/vj26.md) |
| Loads | Use CFD blade-pressure/force results and structural analysis; `3D` CFD is more appropriate when blade loading and tip effects matter. (source: sources/vj29.md) |
| Rated power and rated speed | Generate a power curve over wind speed, then identify the wind speed where the design reaches its chosen rated power. (source: sources/HRI2526.md, sources/vj22.md) |
| Torque ripple | Save torque over a complete rotor revolution and look at how much it rises and falls. (source: sources/vj11.md, sources/va7.md) |

### Important CFD Honesty Rules

- Treat `2D` CFD as useful for early design, airfoil comparison, and trends, not as final proof of absolute performance. (source: sources/vj29.md)
- The review reports that `2D` URANS can overpredict `Cp` by about `15-30%` compared with validated `3D` simulation; some optimistic cases can be worse. (source: sources/vj11.md, sources/vj29.md)
- Check mesh independence, time-step or azimuth-step sensitivity, and domain size before believing a difference between two geometries. (source: sources/va10.md, sources/va14.md, sources/va26.md)
- Startup is especially uncertain in simulation because the startup transient has shown poorer agreement with experiments than steady operation. (source: sources/vj26.md)

### Recommended First SimScale Turbulence Model

For a first VAWT learning model in SimScale, start with **transient `k-omega SST` URANS** and a rotating domain around the rotor.

Why this is a good starting point:

- The HRI SimScale workflow used stationary and rotating domains with a `k-omega SST` turbulence model. (source: sources/HRI2526.md)
- The VAWT review identifies URANS with `k-omega SST` as the main design-stage method. (source: sources/vj11.md)
- `k-omega SST` is commonly used when separated flow and adverse pressure gradients matter around turbine blades. (source: sources/va10.md, sources/vj11.md)
- It is much less computationally expensive than LES or hybrid RANS-LES. (source: sources/va10.md)

For a first comparison:

1. Use the same mesh, domain, wind speed, TSR, and number of revolutions for every design.
2. Change only one design parameter.
3. Run long enough for the transient torque to reach a repeating pattern.
4. Average torque and `Cp` over several complete revolutions after the initial transient.
5. Check mesh refinement before trusting a small performance difference.

Do not begin with LES. It may provide more wake and dynamic-stall detail, but it is more computationally expensive and harder to set up correctly. Use transition SST or DES/LES later if your question specifically concerns low-Reynolds-number transition, deep dynamic stall, or detailed wake structures. (source: sources/va10.md, sources/vj5.md, sources/vj11.md)

Important limitation: a steady-state turbulence model or a simple steady rotating result will not reliably predict actual self-starting. Use a transient startup simulation or physical test for that question, and treat the result cautiously. (source: sources/vj26.md)

### Fast SimScale Learning Plan

The goal is not to learn all of SimScale. Learn one complete, repeatable VAWT comparison workflow.

#### Session 1: Learn The Interface

Practice only these operations:

1. Create a project.
2. Upload a simple CAD model.
3. Check and repair geometry.
4. Create or extract the surrounding fluid volume.
5. Create a mesh.
6. Create an incompressible fluid-flow simulation.
7. Set boundary conditions and run a short job.
8. Open the result in the post-processor.

Use a simple airfoil or cylinder first instead of a VAWT. SimScale's official documentation separates CAD preparation, analysis types, simulation setup, meshing, post-processing, tutorials, and validation cases; learn those basic stages before adding rotating machinery. (source: `https://www.simscale.com/docs/`)

#### Session 2: Learn Rotation

Use a simple three-bladed H-rotor rather than VA9 or VJ20 at first.

Learn these ideas:

- stationary outer fluid domain
- rotating inner fluid region around the rotor
- interface between stationary and rotating regions
- transient time stepping
- fixed wind-speed inlet
- pressure outlet
- wall treatment and near-wall mesh
- torque measurement on the blades or rotor

The HRI SimScale workflow used stationary and rotating domains with `k-omega SST`, which is why this is the recommended first VAWT setup. (source: sources/HRI2526.md)

#### Session 3: Get A Cp Curve

Pick one wind speed and hold it constant. Run the same rotor at several TSR values, such as:

- `TSR = 1`
- `TSR = 2`
- `TSR = 3`
- `TSR = 4`
- `TSR = 5`

For each TSR, calculate the required rotor speed:

`omega = TSR * V / R`

where `omega` is angular speed in rad/s, `V` is wind speed in m/s, and `R` is rotor radius in m.

Then calculate:

`Cp = P / (0.5 * rho * A * V^3)`

and:

`P = Q * omega`

where `P` is mechanical power, `Q` is average torque, `rho` is air density, and `A` is swept area. (source: sources/HRI2526.md, sources/vj20.md)

Plot `Cp` against TSR. That plot is your first performance curve.

For example, using a `0.173 m` radius rotor at `4.8 m/s` and `TSR = 3`:

`omega = 3 * 4.8 / 0.173 = 83.2 rad/s`

This is approximately `795 rpm`. This is an example calculation, not a recommended VA9 operating speed.

#### Session 4: Change One Thing

Once one baseline produces a stable curve, duplicate the simulation and change exactly one item:

- blade pitch
- blade count
- chord
- airfoil
- solidity
- blade-end geometry

Keep everything else identical. Compare:

- average torque
- torque ripple
- peak `Cp`
- TSR at peak `Cp`
- blade force history
- wake behavior

This is a comparative study, not yet a claim about the turbine's final real-world performance. CFD results depend on mesh quality, domain size, time step, turbulence model, and whether the model is `2D` or `3D`. (source: sources/va10.md, sources/vj6.md, sources/vj29.md)

#### Do Not Start With These

- Do not begin with the full VA9 EN0005 geometry; its custom profile and angled blade ends add uncertainty.
- Do not begin with the full VJ20 hybrid; its two coupled rotors add setup complexity.
- Do not begin with LES; it is more expensive and harder to debug. (source: sources/va10.md)
- Do not interpret the first successful run as validation.
- Do not compare two designs if they used different wind speeds, TSR values, mesh quality, or averaging windows.

#### The Minimum Successful First Project

Your first useful SimScale result is not a perfect turbine. It is:

- one simple rotor
- one working rotating-domain simulation
- one mesh check
- five TSR runs
- one `Cp`-versus-TSR plot
- one documented geometry change
- one honest comparison

After that, move toward VA9 or VJ20.

### The Short Answer

For an initial design, use:

1. CAD for geometry
2. A fast rotor-performance model for screening
3. CFD for detailed comparison of a few finalists
4. A prototype or wind-tunnel test for validation

Do not say a design is better just because one CFD result gives a higher `Cp`. First check that the two designs were tested at the same wind speed, TSR/RPM, boundary conditions, mesh quality, and number of simulated revolutions. (source: sources/va10.md, sources/vj6.md, sources/vj29.md)

## Example Tradeoff: VA9 Versus VJ20 At BOS

The five-year BOS dataset contains `37,767` wind observations. Its calculated average wind speed is about `4.755 m/s`; the project notes separately summarize the BOS average as about `4.8 m/s`. (source: `attachments/wind data/BOS_07.21_to_07.26.json`, `active/analysis/brainstorm.md`)

Using the reported values:

- VA9: `Cp = 0.416`, cut-in `1.25 m/s`. (source: `sources/va9.md`)
- VJ20: `Cp = 0.486`, full-scale cut-in `2.81 m/s`, rated speed `7.5 m/s`. (source: `sources/vj20.md`)

For a first-pass comparison, use the wind-power relationship:

`P = 0.5 * rho * A * Cp * V^3`

If air density `rho`, swept area `A`, generator efficiency, and `Cp` are treated as equal or constant, compare each observation using `Cp * V^3`. This is an energy proxy, not a final annual-energy prediction.

### What The BOS Data Says

| Quantity | VA9 | VJ20 |
| --- | ---: | ---: |
| Cut-in threshold used | `1.25 m/s` | `2.81 m/s` |
| Observations at or above cut-in | `95.86%` | `79.80%` |
| Constant-`Cp` proxy, same swept area | `81.03` | `93.80` |
| VJ20 proxy relative to VA9 |  | `1.158x` or about `15.8%` higher |

The lower VJ20 cut-in availability removes about `16.1%` of observations, but those missing winds are mostly low-speed observations and contribute little energy because available wind power scales with `V^3`. With the simplified uncapped assumption, VJ20's higher `Cp` more than covers the lost low-speed operation.

The break-even VJ20 `Cp` in this simplified comparison is approximately `0.420`. That is, if VJ20 could maintain a `Cp` above about `0.420` over its operating wind range, it would beat VA9's `Cp = 0.416` despite the higher cut-in. This conclusion is only valid for equal swept area and equal non-aerodynamic efficiency.

### Why The Result Is Not Settled

VJ20's reported rated speed is `7.5 m/s`. If its output is capped at the rated power associated with that speed, while VA9 is unrealistically allowed to keep increasing as `V^3`, the simple proxy reverses: VJ20 becomes about `14%` lower than VA9. That comparison is not fair enough to choose a design because VA9's actual rated-power curve is not available and the VJ20 source contains multiple scale contexts. (source: sources/vj20.md, sources/va9.md)

The correct next comparison is therefore not just two `Cp` values. It needs:

- each design's `Cp` versus TSR curve
- each design's operating TSR or RPM control strategy
- each design's swept area
- each design's power curve and rated-power limit
- generator and drivetrain efficiency
- actual startup behavior below and near cut-in

> Inference: based on the available BOS data alone, the VJ20 higher-`Cp` advantage appears large enough to compensate for its higher cut-in under an uncapped constant-`Cp` model, but the conclusion can reverse once realistic rated-power limits are included.

## Comparing Full Cp-versus-TSR Curves: VA9 And VJ20

The full curves provide more useful information than comparing only the two peak values, but the published curves are not a perfectly controlled comparison.

### VA9 Curve

The VA9 `Fig. 18` curve models a five-bladed Darrieus rotor with a `4.6 m` height, `2 m` radius, `0.30 m` profile chord, and `12 m/s` wind speed. It compares EN0005 against NACA0012 and NACA0018. (source: sources/va9.md)

Approximate visual features of the EN0005 curve:

- `Cp` is about `0.02` at `TSR = 1`.
- It rises to about `0.29` at `TSR = 4`.
- It reaches about `0.37` around `TSR = 6.5-7.5`.
- It declines gradually to about `0.21` by `TSR = 12`.
- The source concludes that EN0005 performs better than the comparison profiles at higher TSR. (source: sources/va9.md)

These values are approximate readings from the plotted curve, not a source-provided numerical data table.

### VJ20 Curves

The VJ20 `Cp`-versus-TSR figures show the proposed hybrid at wind speeds of `3`, `3.64`, and `5 m/s`. The proposed hybrid peaks near `TSR = 3`, with the source reporting a maximum `Cp` of `0.478` in the wind-speed-specific results and `0.486` in the main comparison. (source: sources/vj20.md)

Approximate visual features of the proposed-hybrid curves:

- `Cp` is already roughly `0.04-0.06` at `TSR = 1`.
- It rises to roughly `0.20-0.34` by `TSR = 2`, depending on wind speed.
- It peaks around `0.40-0.48` near `TSR = 3`.
- It remains roughly `0.30-0.42` around `TSR = 3.5-4`.
- It falls to roughly `0.10-0.16` around `TSR = 5`.
- The hybrid's reported static torque coefficient is positive at all azimuth angles in the tested cases, which supports its self-starting claim. (source: sources/vj20.md)

### Curve-to-Curve Interpretation

| TSR region | Apparent advantage | Interpretation |
| --- | --- | --- |
| `TSR = 1-2` | VJ20 | VJ20 produces more modeled power at low-to-moderate TSR and is designed to have stronger starting torque. (source: sources/vj20.md) |
| `TSR = 2-4` | VJ20 | VJ20's reported peak occurs near `TSR = 3`, while the compared H-rotor reference peaks near `TSR = 2.62`. (source: sources/vj20.md) |
| `TSR = 4-5` | Depends on wind case | VJ20 remains useful but begins declining after its peak; its curve is still above the compared Darrieus case in the published VJ20 comparison. (source: sources/vj20.md) |
| `TSR = 5-12` | VA9 EN0005 | The VA9 model continues into a high-TSR operating range and remains around `Cp = 0.21` at `TSR = 12`. (source: sources/va9.md) |

### What This Means For BOS

The curves suggest two different operating strategies:

- **VJ20:** design around moderate TSR, approximately `2-4`, where the hybrid's peak `Cp` and positive static torque are reported.
- **VA9:** design around a broader or higher TSR range, approximately `5-8` for the modeled EN0005 case, while retaining special geometry for startup.

If the generator and controller allow variable speed, each turbine could be operated near its best TSR as wind speed changes. In that case, VJ20's higher peak `Cp` could be valuable. If the turbine operates at a fixed or poorly controlled rotational speed, the shape of the entire curve matters more because the rotor may spend much of its time away from its optimum TSR.

The main limitation is that the VA9 and VJ20 curves use different rotor geometries, wind speeds, blade counts, Reynolds numbers, modeling/experimental contexts, and likely different swept areas. Therefore, the curves can show the designs' operating tendencies, but they cannot by themselves establish which turbine produces more annual BOS energy. (source: sources/va9.md, sources/vj20.md)

> Inference: for a BOS design study, VJ20 is the stronger candidate if the design can maintain operation near `TSR = 3`; VA9 is the stronger candidate if its high-TSR performance and experimentally demonstrated startup are more important than matching VJ20's peak `Cp`.

## Future Lessons

Add later learning here, including:

- Understanding TSR with worked examples
- Calculating swept area and available wind power
- Solidity, chord, radius, and blade-count relationships
- Lift, drag, angle of attack, and dynamic stall
- Reading `Cp` versus TSR curves
- Comparing published `Cp` versus TSR curves fairly
- Choosing a first performance-model and CFD workflow
- Choosing a turbulence model in SimScale
- A fast SimScale learning plan for VAWTs
- Quantifying cut-in versus `Cp` tradeoffs with a wind-speed histogram
- Selecting a first H-rotor baseline
- Modeling and validating a VAWT

## Related Notes

- [[Wind Turbine Parameters]]
- [[VAWT Aerodynamic Design Parameters]]
- [[Design Checklist]]
- [[Optimization]]
- [[va9 EN0005 Self-start Darrieus VAWT]]
