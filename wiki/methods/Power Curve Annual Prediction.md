---
Created: 2026-07-06
Updated: 2026-07-07
Sources: [[vj13]]
Source_count: 1
Tags: #methods
---
## Power Curve Annual Prediction

Method for estimating annual cluster output by fitting power curves and combining them with site wind roses. (source: sources/vj13.md)

- The isolated turbine power is fitted as `Pi = 0.1454·Uin^3`. (source: sources/vj13.md)
- The cluster power is fitted with a cubic polynomial in wind speed for each wind direction and installation orientation. (source: sources/vj13.md)
- Hourly wind speed and direction data from three airports are then mapped onto those fitted curves to estimate annual power output. (source: sources/vj13.md)
- The method avoids running a full CFD case for every hour of the year, reducing the annual evaluation cost from 8760 direct simulations per site. (source: sources/vj13.md)

Related: [[Annual Energy Output]], [[AEO Calculation]], [[vj13 Cluster Installation Orientation]], [[Urban Wind Conditions]]

#methods
