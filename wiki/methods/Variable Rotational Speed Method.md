---
Created: 2026-07-06
Updated: 2026-07-06
Sources:
- [[vj13]]
Source_count: 1
Tags:
- methods
---

## Variable Rotational Speed Method

Method for adjusting turbine rotational speed during simulation so each turbine follows its local optimal power point. (source: sources/vj13.md)

- The paper implements the control strategy with a UDF in Fluent and the `ZONE_MOTION` macro. (source: sources/vj13.md)
- The turbine speed is updated from power measured over a time window and is considered converged when the rotational-speed difference stays below `0.5 rad/s` over 10 time ranges. (source: sources/vj13.md)
- Cut-in speed is `2 m/s` and cut-out speed is `15 m/s`. (source: sources/vj13.md)
- When `F < 0.1`, the paper sets rotational speed to `0 rad/s` because the turbine is effectively stalled. (source: sources/vj13.md)
- The method removes the strong dependence on the initial relative phase angle that appears under fixed-speed simulation. (source: sources/vj13.md)

Related: [[CFD and Validation]], [[Power Curve Annual Prediction]], [[Savonius Wind Turbine Cluster]]

#methods
