#Computer-Science #artificial-intellegence 

in algorithms related to pathfinding, a [[Heuristic Function]] is said to be admissible if it never overestimates the actual cost of reaching the goal from any given node. It is related to the concept of [[Consistent Heuristics]]. While all consistent heuristics are admissible, not all admissible heuristics are consistent.
Here is an example of an admissible heuristic:

- [[Manhattan Distance]] is a heuristic function that is used to estimate the cost of reaching the goal in a maze. The Manhattan distance between two points is the sum of the horizontal and vertical [[Coordinate Geometry & Vector|Coordinates]] between them.

A heuristic function h(n) is admissible if it satisfies the following condition for every node n in the graph:

$$0 ≤ h(n) ≤ h*(n)$$
Where,
- **h(n)** is the value returned by the heuristic function for node n (the estimated cost from node n to the goal).
- **h*(n)** is the true cost (the actual minimum cost) from node n to the goal.

## Creating Admissible Heuristic
There are many ways to create admissible heuristic functions. Some of them are-
- Often admissible heuristics are solutions to [[Relaxed Problem]]s, where new actions are available.
- 