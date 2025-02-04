- search used when the path does not matter/systematic search is not possible
### Local Search Algorithms
- in many optimization problems, the path to the goal is irrelevant and the goal state itself is the solution
- State space is the set of "complete" configurations
#### Idea
- keep a single "current" state, and try to improve it
- Move only to neighbors of that node
#### Advantages
- no need to maintain a search tree
- use very little memory
- can often find good enough solutions in continuous or large state spaces
### Trivial Algorithms
- Random Sampling
	- generate a state randomly
- Random Walk
	- randomly pick a neighbor of a current state
- Both algorithms are asymptotically complete
### Local Search Algorithms
1. Hill Climbing
2. Simulated Annealing
3. Local Beam Search

### Hill Climbing (Greedy Local Search)
- search moves uphill; moves in the direction of increasing elevation/value to find the top of the mountain
- terminates when it reaches a peak
#### 8-Queens Problem
- State - all queens on the board
- Successor function - move a single queen to another square in the same column
- Heuristic Function:
	- number of pairs of queens that are on the same row, column, or diagonal
- Given randomly generated 8-queens starting states
	- 14% of the time, it solves the problem
	- 86% of the time, it gets stuck at a local minimum
- However
	- It takes only 4 steps on average when it succeeds
	- and 3 on average when it gets stuck
	- For a state space with 17 million states, that's pretty good
#### Problems of Hill Climbing
- often gets stuck at the following:
	1. Local maximum 
		- peak that is higher than each of its neighboring states, but lower than the global maximum
	2. Ridge
		- result in a sequence of local maxima
	3. Plateau
		- an area of the state space landscape where the evaluation function is flat
		- can be a flat local maximum, or a shoulder, from which it is possible to make progress
		- a hill-climbing search may be unable to find its way of the plateau
### Hill Climbing Variants
##### 1. Sideways Moves
- sideways moves escape from plateau where best successor has same value as the current state
- if we always allow sideways moves when there are no uphill moves, an infinite loop will occur where the algorithm reaches a flat local maximum that isn't a shoulder
- Common solution: put a limit on the number of consecutive sideways moves allowed
##### 2. Stochastic Hill Climbing
- chooses at random from among the uphill moves
- probability of selection can be dependent on steepness of uphill move
- usually converges more slowly than steepest ascent, but in some state landscapes, it finds better solutions
##### 3. First Choice Hill Climbing
- implements stochastic hill climbing by generating successors randomly until one is generated that is better than the current state
- good strategy when a state has many successors
##### 4. Random-Restart Hill Climbing
- conducts a series of hill-climbing searches from randomly generated initial states; stopping when a goal is found
- it is complete with probability approaching 1, for the trivial reason that it will eventually generate a goal state as the initial state
#### Takeaways from Hill Climbing Search
- effectivity depends on the shape of the state-space landscape
	- if there are few local maxima and plateaux, random-restart hill climbing will find a good solution very quickly
- many real-world problems are NP-hard problems which typically have an exponential number of local maxima to get stuck on
- a reasonably good local maximum can often be found after a small number of restarts
### Simulated Annealing
- essentially a combination of hill climbing and random walk to utilize efficiency from hill climbing and completeness from random walk
- essentially starting at a high displacement (shaking) constant, and then gradually reducing the intensity
### Local beam Search
- keeps track of $k$ states rather than just one
-  not the same as $k$ random-restart searches
- In a random-restart search, each search process runs independently of the others
- useful information is passed among the parallel search threads. In effect, the states that generate the best successors will be prioritized by the algorithm, essentially abandoning unfruitful searches
### Stochastic beam search
- instead of choosing the top successors, choose the **successors with probability proportional to the successor's value**
### Evolutionary Algorithms
- can be seen as variants of stochastic beam search that are explicitly motivated by natural selection
- there is a population of individuals (states), in which the fittest (highest value) individuals produce offspring (successor states) that populate the next generation, a process called recombination
