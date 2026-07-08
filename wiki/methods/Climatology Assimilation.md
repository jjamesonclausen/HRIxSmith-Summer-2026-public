---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[va18]]
Source_count: 1
Tags: #methods
---
## Climatology Assimilation

CFD-aided method that reconstructs a spatial wind-resource climatology from measured wind statistics at one reference point, then extrapolates those statistics across the full domain. (source: sources/va18.md)

![Source figure](../../images/va18-fig12.jpg)
Original caption: Figure 12. [[va18|Source]]
![Source figure](../../images/va18-fig15.jpg)
Original caption: Figure 15: Input climatology for background Climatology Assimilation at MT1 90m [[va18|Source]]

- The source's local version assimilates long-term climatology measured at one point inside the computational domain and reconstructs three-dimensional fields of mean wind speed, Weibull shape `k`, Weibull scale `A`, wind power density, and turbulence intensity. (source: sources/va18.md)
- In the paper's validation test, statistics from `MT2` at 20 m were assimilated and extrapolated 364 m to `MT1` at 20 m. (source: sources/va18.md)
- The extrapolated local-assimilation result preserved the main site-to-site trend, with simulated speed and power ratios of 1.11 and 1.35 compared with measured ratios of 1.10 and 1.42. (source: sources/va18.md)
- A background-assimilation variant uses climatology from MIT's Green Building at about 90 m height when local long-term measurements are unavailable. (source: sources/va18.md)
- The paper also combines TopoWind with the same workflow to transfer airport climatology physically before applying the local urban CFD model. (source: sources/va18.md)
- The source explicitly treats the approach as promising but only preliminarily validated; it says more work is needed to quantify method accuracy. (source: sources/va18.md)

Related:
- [[CFD]]
- [[CFD and Validation]]
- [[Urban Wind Conditions]]

#methods
