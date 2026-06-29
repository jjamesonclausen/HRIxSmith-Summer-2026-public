## Multi-Island Genetic Algorithm (MIGA)

A genetic algorithm variant that splits the population into multiple islands that evolve separately and periodically exchange individuals. (source: sources/va2.md)

![Figure 13: MIGA and surrogate model optimization flowchart](../../images/va2-fig13.jpg)

- Each island performs selection, crossover, and mutation independently. (source: sources/va2.md)
- Migration helps global search and reduces premature convergence risk. (source: sources/va2.md)
- In this paper, MIGA used 10 islands, population size 40, crossover probability 0.85, mutation probability 0.02, and migration every five generations. (source: sources/va2.md)
- The optimizer was coupled to a Kriging surrogate to reduce CFD evaluations. (source: sources/va2.md)

Related: [[Kriging Surrogate Model]], [[CST Parameterization]], [[CFD]]

#methods