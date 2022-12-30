# Genetic-Blotto
Using a genetic algorithm to find an optimal solution to the Blotto Game

# Overview
In this variation of the Blotto Game (https://en.wikipedia.org/wiki/Blotto_game), two generals attempt to capture a sequence of ten castles numbered 1 - 10. Each general has an army of 100 soldiers. In the beginning of the game, each general allocates a number of soldiers to attack each of the ten castles. The generals then reveal their army allocations to each other. For each castle, whichever general allocated more soldiers to attack it wins the castle. If the number of soldiers allocated to a castle is the same  Castle number x is worth x points, whomever wins more points is the winner.

Additional 'knockout' rule: if a general wins three consecutive castles, they win all of the succeeding castles regardless of the number of soldiers allocated to them. E.g. if a general wins castles 5, 6, 7, castles 8, 9, 10 are won as well.

Example game:

|Castle|1  |2  |3  |4  |5  |6  |7  |8  |9  |10 |
|------|---|---|---|---|---|---|---|---|---|---|
|General A|10|10|10|10|10|10|10|10|10|10|
|General B|5|10|15|17|8|5|5|15|18|2|

Outcome: A wins castles 1, 5, 6, 7, 8, 9, 10 for a score of 46 points, B wins castles 3, 5 for a score of 7 points. 

# Genetic Algorithm Formulation

**Genotype/Phenotype**: a list of ten integers that sum to 100, representing the allocation of soldiers to each castle

**Mutation**: generation of mutated offspring: weighted average sum of parent allocation (70%) and random allocation from a uniform distribution (20%).

**Crossover**: given two genotypes, randomly pick a number from 2 - 10. Swap the allocations of the two genotypes for all castles after and including the number. 

**Selection**: make all pairs of genotypes in the pool compete. Pick the n genotypes with the highest score to as the parents for the next generation.
