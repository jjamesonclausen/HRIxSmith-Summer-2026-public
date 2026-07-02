---
Created:
Updated: 2026-07-02
Sources: [[va2]]
Source_count: 1
Tags:
- summaries
---

## va2 Summary

Airfoil optimization study for an H-type vertical-axis wind turbine using CST parameterization, a Kriging surrogate model, and a multi-island genetic algorithm (MIGA). (source: sources/va2.md)

- The baseline airfoil is NACA0015, expressed with CST and validated with CFD against a wind-tunnel benchmark. (source: sources/va2.md)
- Seven design variables were selected from an initial 13-parameter CST description. (source: sources/va2.md)
- CST turns the airfoil shape into a compact coefficient set using a class function and Bernstein-polynomial shape terms. (source: sources/va2.md)
- The paper used 70 Latin-hypercube samples, with 80% for training and 20% for validation. (source: sources/va2.md)
- Kriging is written as a deterministic drift term plus a stochastic residual; the paper uses an exponential kernel and reports R2 = 0.91368. (source: sources/va2.md)
- The optimization target was maximum Cp at TSR = 1.8, with thickness and variable-range constraints. (source: sources/va2.md)
- MIGA searched the surrogate model using multiple islands, migration, crossover, and mutation. (source: sources/va2.md)
- The Kriging surrogate model reached R2 = 0.91368 with 70 training samples and 10 validation samples. (source: sources/va2.md)
- MIGA was used to optimize the airfoil under a TSR-based objective and thickness constraints. (source: sources/va2.md)
- The best airfoil improved Cp by 14.2% at TSR > 1.5, and average efficiency improved by 9.8%. (source: sources/va2.md)
- Pressure and velocity fields show reduced leading-edge pressure and weaker trailing-edge separation after optimization. (source: sources/va2.md)

Inference notes:
- `Inference:` Latin-hypercube sampling is used here to spread designs across the variable space more evenly than simple random sampling. (source: sources/va2.md)
- `Inference:` the exponential kernel means nearby designs are treated as more similar, with similarity decaying as distance increases. (source: sources/va2.md)
- `Inference:` the surrogate model is the cheap evaluator, while MIGA is the search procedure that proposes candidates. (source: sources/va2.md)

Related concepts: [[H-VAWT]], [[Kriging Surrogate Model]], [[CST Parameterization]], [[Multi-Island Genetic Algorithm]]

#summaries
