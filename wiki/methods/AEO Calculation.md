## AEO Calculation

Method for estimating the annual energy output (AEO) of a wind turbine using wind distribution and power curves. (source: sources/g1.md)

- Wind speed distribution is divided into bins (e.g., 1 m/s intervals). (source: sources/g1.md)
- For each bin:
  - Determine probability of wind speed occurrence. (source: sources/g1.md)
  - Multiply by total annual hours (8760 h). (source: sources/g1.md)
  - Multiply by turbine power output at that wind speed (from power curve). (source: sources/g1.md)
- Sum contributions across all bins to obtain total AEO. (source: sources/g1.md)

> Inference: Accuracy depends heavily on quality of wind data and validity of the turbine power curve.

Related: [[methods/Bin Method]], [[concepts/Annual Energy Output]]
