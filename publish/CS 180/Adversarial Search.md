- strategy used when a search may be deemed obsolete due to an opponents move
- You cannot search the entire space from the outset looking for a solution since your opponent may make a move that makes any path you find obsolete
## Multiagent Environment + Competition
- Agents have different goals -> adversarial search
	- **Idealized setting** in which players with **divergent goals** take **turns** in performing actions
	- Agents can perform only **"legal moves"** (as defined by the rules of the game)
	- Moves are chosen according to a **strategy** that specifies a move for every possible move of the opponent
	- The game is won when one of the agents achieves their objectives (as measured by a **utility function**)
### Types of Games (Classification Criteria)
##### Number of players
- Two players (e.g. chess, checkers)
- Multiplayer: mixed competitive / cooperative strategies (e.g. temporary alliances)
##### Properties of the utility function
- Zero-sum
	- sum of utilities of the agents is zero, independent of game outcome (e.g. chess, checkers)
- Variable sum
	- not zero-sum; may lead to complex optimal strategies, sometimes involving collaboration (e.g. monopoly, backgammon)
##### Information available to Players
- **Perfect Information** (e.g. chess checkers)
- **Partial Information** (e.g. most card games)
##### Elements of Chance
- **Deterministic** (e.g. chess, checkers, go)
- **Stochastic** (e.g. backgammon)
##### Time Constraints
- **Unlimited / limited time** (e.g. chess with a clock)
- **Unlimited / limited moves** (e.g. chess in 40 moves)
## Games as Search Problems
- Games are an idealization of worlds in which
	- the world state is fully accessible
	- the actions are well-defined
	- uncertainty due to:
		- moves by the opponent
		- due to the complexity of games
- Games are usually much too hard to solve
- Example: Chess
	- Average branching factor: 35
	- Average moves by each player: 50
	- Total number of nodes in search tree: $35^{100}$
	- Time limits for making good decisions
## Games and AI
- Games have time limits
	- execution efficiency is very important
	- games have spurred the development of any-time algorithms
- All games are contingency problems
	- game-playing agent must calculate a whole tree of actions where each branch deals with what the opponent will do
- **Dealing with Time Limits**
	- using techniques that allow us to ignore portions of the search tree that make no difference to the final choice
	- need heuristic evaluation functions that measure how good a position is without doing a complete search
- Purpose of heuristic function: reduce the search space to be explored
## Game Formalization
1. Initial State
	- How does the game start?
2. Successor Function
	- A list of legal (move, state) pairs for each state
3. Terminal Test
	- Determines when game is over
4. Utility Function
	- Provides numeric value for all terminal states
5. Game Tree
	- The state space
### Minimax
- Consider a 2-player game (with players MAX and MIN)
- We want MAX to win
	- MAX will try to maximize the value of the pay-off function
	- MIN will try to minimize the value of the pay-off function
#### Example: Tic-Tac-Toe
- Initial State: Empty 3x3 board
- Moves: Place a stone (MAX: x, MIN: o) on an empty board square
- Terminal Test: three stones from the same player are aligned
- The game tree is relatively small - fewer than 9! = 362,880
	- 9! since number of possible stone placements decreases per turn
## Optimal Strategies
- Find the contingent strategy for MAX assuming an infallible (not throwing) MIN opponent
- Assumption: both players play **optimally**
- Given a game tree, the optimal strategy can be determined by using the minimax value of each node:
	![[Pasted image 20250205145455.png]]
## Minimax Algorithm
1. Generate the entire game tree up to the terminal states
2. Compute the pay-off of each terminal state using the utility function
3. Use the pay-off values of the terminal states to determine the pay-off values of the nodes one level higher up in the search tree. 
	- Payoff value for a higher level node is:
		- lowest pay-off of the nodes children if it is **MIN's turn**
		- highest pay-off of the nodes children if it is **MAX's turn**
4. Continue backing up the values from the leaf nodes toward the root, one level at a time.
5. When the root node is reached, the branch that leads to the highest pay-off should be chosen by MAX
#### Minimax Example:
![[Pasted image 20250205152406.png]]
#### Minimax Evaluation
- Complete: Yes (if tree is finite)
- Optimal: Yes (against an optimal opponent)
- Time Complexity: $O(b^m)$
- Space Complexity: $O(bm)$ (depth-first exploration)
#### Comments on Minimax
- assumes that the opponent plays perfectly
- If max depth of tree is $m$, and there are $b$ legal moves for each node, the time complexity of minimax is $O(b^m)$, which makes this algorithm impractical
- Space complexity is linear in $m$ and $b$ since minimax is depth-first search: $O(bm)$ 
- computes the optimal playing strategy but does so inefficiently because it generates a complete tree and then computes and backs up a static evaluation function
- Basic idea: "if you have an idea that is surely bad, don't take the time to see how truly awful it is."
#### Generalized Minimax
- If the game is not zero-sum, or has multiple players
- Generalization of minimax:
	- Terminals have utility tuples
	- node values are also utility tuples
	- each player maximizes its own component
	- can give rise to cooperation and competition dynamically
	![[Pasted image 20250205153959.png]]
## Alpha-beta Pruning
- Store at each node an interval $[\alpha, b]$ that contains the minimax value of the node, and update the estimates of the bounds of the interval as the search proceeds
- **$\alpha$** is the value of the best choice for MAX (i.e. highest value) found so far
- $\beta$ is the value of the best choice for MIN (i.e. lowest value) found so far
	- $\beta$ values can never increase for a MIN node
- Use **DFS** for tree traversal
#### Rules for Stopping Search
1. $\alpha$-cutoff: Stop search at MIN node whose **$\beta$-value $\leq$ $\alpha$-value** of any of its MAX antecessors
2. $\beta$-cutoff: Stop search at MAX node whose $\alpha$-value $\geq$ $\beta$-value of any of its MIN antecessors
##### Example:
![[Pasted image 20250205170932.png]]
##### Alpha-Beta Evaluation
- Pruning does not affect final result
- Alpha beta only needs to examine $O(b^{d/2})$ nodes to pick the best move
- For chess, effective branching factor is reduced to $\sqrt{b}$ instead of $b$ (about 35 to about 6)