# Brainstorming
See [[Design goal]]

## Wind data

https://mesonet.agron.iastate.edu/request/asos/1min.phtml

collected at 9m from ground

Avg wind speed: 4.8 m/s
Avg gusts: 6.3 m/s

Figure 1: Histogram of hourly wind speed from Jul 2025 - July 2026. There are significant gaps so only about 73% of the year is represented. For AEO calculations we will use a 5 year span.

![[BOS_07.25_to_07.26_histogram.svg]]


## Design thoughts

- Most Darrieus turbines have rated speed around 10-15 m/s and cut-out speed around 20 m/s according to the LLM wiki
- Va9 EN0005 Darrieus turbine has a cut in speed < 2 m/s!
- should design turbine to be at a similar height as wind measurements for best estimations of power production. (Wind speed can vary dramatically in the turbulent boundary layer near the ground.)
- 
