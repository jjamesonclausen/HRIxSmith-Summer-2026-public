---
Created: 2026-07-06
Updated: 2026-07-07
Sources:
  - "[[va19]]"
Source_count: 1
tags:
  - methods
---
## Measure-Correlate-Predict (MCP)

Method for using a short on-site measurement campaign together with a long-term reference station to estimate long-term wind conditions at the site of interest. (source: sources/va19.md)

![Equation](va19-eq1.jpg)
Original caption: Equation 1. Correlation. [[va19|Source]]
![Source figure](va19-fig23.jpg)
Original caption: Figure 23. Location of Beverly Municipal Airport in relation to Cambridge. [[va19|Source]]

- In `va19`, campus measurements were correlated with long-term hourly observations from Beverly Municipal Airport because the airport offered about 30 years of historical weather data and a better coastal match than Logan. (source: sources/va19.md)
- The workflow first computes the mean and standard deviation for the short overlapping period at both the site and the reference station. (source: sources/va19.md)
- It then uses the correlation equation from Manwell's Hull Wind II case study to predict site wind speed from historical airport wind speed. (source: sources/va19.md)
- The report says this makes it possible to estimate what wind speed at the MIT sites would have been over roughly 1990-2006 and then use those reconstructed speeds for annual energy and payback analysis. (source: sources/va19.md)
- The same source warns that short logging time increases uncertainty; its Appendix C reports larger prediction error at Eastgate because of intermittent data collection. (source: sources/va19.md)

Related:
- [[Urban Wind Conditions]]
- [[Payback Period Analysis]]
- [[CFD]]

#methods
