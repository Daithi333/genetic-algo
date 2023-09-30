# genetic-algo

Genetic algorithm to solve the Knapsack problem.

The basic building block are:

 - Genetic representation of a solution (Genome)
 - Population function to generate new solutions (List of Genomes)
 - Fitness function to evaluate a solution
 - Selection function to select parent Genomes for the next generation, inclined towards better fitness scores
 - Single-point cross-over function which takes 2 genomes and slices them at a random point and crosses over the parts
 - Mutation function to randomly mutate a Genome with a certain probability (or leave as is)


## Run Evolution function

Loop to simulate evolution.

1. Generate initial population
2. sort population by highest fitness, for checking against fitness limit or in case you want to implement elitism
3. Check against fitness limit and break out of loop if reached or exceeded
4. Start building the next generation with top 2 solutions from this generation
5. Generate all other solutions for next generation by:
     - looping through half the length of the population minus 1 (as we will be creating 2 offspring per iteration)
     - select 2 new parents with the selection function
     - Use the crossover function to generate 2 new offspring
     - Use the mutation function on the offspring introduce some variety
     - Add these offspring to the next generation.
6. Replace population with the next generation and move on to next generation (loop iteration)


### Fitness limit

Things Fitness limit - 740
More Things Fitness limit - 1310

Generally you would not know the optimal solution in advance, so would not be able to provide a fitness limit. 
In that case the max generations would need to be run to find the best, if not optimal solution. 
Max generations could be tweaked to get the right balance between runtime and solution quality
