## va2 Summary

Airfoil optimization study for an H-type vertical-axis wind turbine using CST parameterization, a Kriging surrogate model, and a multi-island genetic algorithm (MIGA). (source: sources/va2.md)

- The baseline airfoil is NACA0015, expressed with CST and validated with CFD against a wind-tunnel benchmark. (source: sources/va2.md)
- Seven design variables were selected from an initial 13-parameter CST description. (source: sources/va2.md)
- The Kriging surrogate model reached R2 = 0.91368 with 70 training samples and 10 validation samples. (source: sources/va2.md)
- MIGA was used to optimize the airfoil under a TSR-based objective and thickness constraints. (source: sources/va2.md)
- The best airfoil improved Cp by 14.2% at TSR > 1.5, and average efficiency improved by 9.8%. (source: sources/va2.md)
- Pressure and velocity fields show reduced leading-edge pressure and weaker trailing-edge separation after optimization. (source: sources/va2.md)

Related concepts: [[H-VAWT]], [[Kriging Surrogate Model]], [[CST Parameterization]], [[Multi-Island Genetic Algorithm]]
