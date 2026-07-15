---
Created: 2026-07-15
Updated: 2026-07-15
Sources:
  - "[[cj3]]"
Source_count: 1
tags:
  - methods
---
## WebPlotDigitizer

Software used to extract numerical data from a plotted figure when the source does not provide a table directly. In `cj3`, it is used to pull reference `Cp` data from a paper before comparing the CFD result to the published curve. (source: sources/cj3.md)

- The transcript uses `WebPlotDigitizer` as a preprocessing step for validation-style comparison, not as a CFD solver. (source: sources/cj3.md)
- In this workflow, the extracted plot data helps define one selected benchmark condition for the Darrieus CFD setup. (source: sources/cj3.md)

> Uncertainty: the transcript does not name the reference paper or show the full digitizing procedure, so this source supports the role of `WebPlotDigitizer` in the workflow, but not a detailed best-practice guide for using the software. (source: sources/cj3.md)

Related: [[CFD]], [[cj3 Darrieus Course CFD Workflow]], [[cj3-summary]]

#methods
