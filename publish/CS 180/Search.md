### Search Problem Formulation
1. State space
	- each state is an abstract representation of the environment
	- the set of all states reachable from the initial state by any sequence of actions
	- the state space is discrete
2. Initial state
	- the state that the agent starts in
	- usually the current state
3. Actions
	- given a particular state *s*, *ACTIONS(s)* returns the set of actions that can be executed in *s*.
4. Successor Function
	- returns the state that results from doing action *a* in state *s*
5. Goal Test
	- determines whether a given state is a goal state
	- enumerated set of states, abstract property
6. Path cost
	- assigns a numeric cost to each path (positive)
	- step cost = cost of action *a* in state *s* to *s'*
	- path cost = sum of step costs
- Each part of the search problem formula, when parsed through a search algorithm, will yield a solution
### Abstraction
- process of removing detail from a representation
### Example: 8-puzzle
![[Pasted image 20250204133212.png]]
- States
	- specifies the location of each of the eight tiles and the blank in one of the nine squares
- Initial State:
	- any state
- Actions:
	- blank moves *left*, *right*, *up*, or *down*
- Successor function
	- generates the legal states that result from trying any of the four actions
- Goal test:
	- checks whether state matches the goal configuration shown in the goal state
- Path cost:
	- each step costs 1, so the past cost is the number of steps in the path
- State space sizes:
	- 3x3: 181,440 states
	- 4x4: 1.3 trillion
	- 5x5: $10^{25}$ 
### Search Algorithms
#### 1. Basic Search
##### Assumptions
1. The environment is **static**
2. The environment is **discretizable**
3. The environment is **observable**
4. The actions are **deterministic**
##### Concepts
1. Search Algorithm
	- takes a search problem as input and returns a solution, or an indication of failure
2. Search tree
	- algorithms that superimpose a search tree over the state-space graph
	- tree that forms various paths from the initial state, trying to find a path that reaches a goal state
3. Node
	- a state in the state space
4. Root
	- initial state of the problem
5. Edge
	- action
6. Search Strategy
	- at each stage, it determines which node to expand
7. Evaluation Terminology
	- **b**: branching factor
	- **d**: depth of shallowest goal node
	- Frontier: nodes that are reachable by expanded (visited) nodes
### Search Strategies
- defined by picking the order of node expansion
- Performance Measures:
	1. Completeness - does it always find a solution if one exists?
	2. Time complexity - number of nodes generated or expanded
	3. Space complexity - maximum number of nodes in memory
	4. Optimality - does it always find a least-cost solution
### Blind vs Heuristic Strategies
##### Blind Strategies
- do not exploit any of the information contained in a state
- Examples:
	- BFS (Breadth-first Search)
	- DFS (Depth-first Search)
		- Depth-limited
		- Iterative deepening
	- Uniform-Cost
##### Breadth-First Strategy
- new nodes inserted at end of frontier (FIFO)
![[Pasted image 20250204134750.png]]
- nodes are visited from **left to right**
- goal test is applied to each node when it is generated rather than when it is selected for expansion
##### BFS Evaluation
- Complete?: Yes
- Optimal?: Yes (if step cost is 1)
- Number of nodes generated: $1+b+b^2+...+b^d$ = $O(b^d)$
- Time and space complexity is $O(b^{d+1})$
##### Depth-First Strategy
- New nodes are inserted at the front of the frontier
- Assumption: expand the leftmost node
![[Pasted image 20250204140723.png]]
##### DFS Evaluation
- b: branching factor
- d: depth of shallowest goal node
- m: maximal depth of a leaf node
- Complete?: only for finite search tree
- Optimal?: No
- Number of nodes generated: $O(b^m)$
- Time Complexity: $O(b^m)$
- Space Complexity: $O(bm)$
##### Depth-Limited Strategy

