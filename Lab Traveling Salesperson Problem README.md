# Lab: Traveling Salesperson Problem 
---
_Write the critical portions of a genetic algorithm to solve the Traveling Salesperson Problem._
## Routines
- `ga_tsp(initial_population, distances, generations)`:which is given an initial population of valid Hamiltonian paths
- `(initial_population, which is a list of paths [tuples])`
- `(distances)`: Dictionary of distances 
- `(generations)`: Number of generations that your algorithm should run.
- `ga_tsp()`: should return the best path (a tuple of cities) from the final generation, after completing the requisite number of generations.
Note that a generation is defined as a single iteration of the algorithm (parent selection, crossover, selection of the fittest population) using a steady population across generations (the same number of children as there are parents).
If you use a variation of the above approach, such as creating half the number of children compared to the population size, you'll need to perform twice the number of iterations (generations).
## Path
- A tuple listing all "cities" in the path.
- The path is assumed to be a **Hamiltonian circuit** that completes by taking an edge from the last city listed back to the first city listed.
## Supporting Files
### util.py
`cost(path, distances)`:
	returns the cost of a path.
	`cost()` checks that the path and distance dictionary are valid and will return None if not, may not detect all invalid paths. (this should cause your code to throw a TypeError if you use the return value).

`valid_path(path)`:
	confirms the path is internally sound (no repetitions).

`best_path(list_of_paths, distances)`:
	returns the best (lowest cost) path in list_of_paths.
### load_dist.py
`load_dist(filename)`:
	Will load a dictionary of distances from the file named filename and can be imported from. The format of filename is individual lines of the form "A, B, distance" where A and B are city names and distance is a positive integer distance.
	A line causes the distance from A to B and B to A to be loaded into the dictionary.
	A line starting with # is a comment. Comment lines and blank lines are ignored.
	`load_dist` also ensures that the distance from a node to itself is always zero.
	You can update the A to B (B to A) distance later in the file -- so if you want to slightly change the topology (aka distances), you can just add a custom update to the end of the file.
	`load_dist()`: returns a list of all the city names and a dictionary of distances.
	`load_dist()`: returns None, None if the file did not load properly.
### tsp.py
if run at the command line with a filename, so % python3 tsp.py filename will load distances from filename, compute an initial population, and call `ga_tsp()` to run 500 generations and report if `ga_tsp()` found a better result than was in the initial population.
### init_pop.py
`init_pop(list, dist)`:
	Contains two routines to create an initial population.
	These routines are defined in tsp.py.
	One version of the routine, take a list of cities and the distance matrix and generates a random set of initial paths of appropriate size.

`init_lousy()`:
	Intentionally creates an initial set of paths with high costs.
### two_opt.py
`two_opt()`:
	Designed to use the lab's cost function.
	You are not required to use 2-opt in your implementation.
	We are providing two sample distance files: DIST6-simple is a simple 6 city world with a clear best path.
	DIST23-basic is a 23 city world divided up into 3 districts (clouds).

If `ga_tsp` is given **None** for any argument it should return **None**. If generations is not positive, `ga_tsp` should return **None**. You can assume distances and `initial_population` are valid if non-None.
## Performance
No requirements for big-O performance.
Tests will be run to see if the Genetic Algorithm finds better results than the best path in the initial population.
## Python Guidance
`Sorted()`:
	`sorted(population, key=partial(cost, distances=dist))`
	can take a list of additional arguments that may be useful.
	To sort a list of paths using the cost function you set the key value in sorted.
	But sorted assumes the key function takes a single value, the item whose cost is to be assessed.
	To tell sorted that cost takes two arguments and assign the value of the second argument, you need to import partial from functools and then write something like:
	`dist` is the dictionary of distances.
	Example in `init_pop.py`.