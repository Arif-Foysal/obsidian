#Algorithm #artificial-intellegence #Computer-Science #GreedyAlgorithm

Greedy Breadth-First Search (Greedy BFS) is an [[Informed search algorithm]] that combines characteristics of both Greedy Search and Breadth-First Search. It uses a  [[Heuristic Function]] to guide the search while exploring the search space in a breadth-first manner.

In a traditional Greedy Best-First Search, the algorithm always selects the node that is estimated to be closest to the goal state based on the heuristic value. It focuses solely on the heuristic information and does not consider the actual cost of reaching that node. However, Greedy Best-First Search can get stuck in loops and may not necessarily find an optimal solution.

### Differences Between BFS and GBFS
![[BFS vs GBFS]]

### Features of Greedy Breadth First Search
- **Heuristic Priority**: Greedy BFS prioritizes nodes with lower heuristic values, favoring nodes that are estimated to be closer to the goal state.
- **Breadth-First Exploration**: The algorithm explores nodes level by level, similar to regular BFS, ensuring that it examines all nodes at a given depth before moving to the next depth level.
- **Time and Space Complexity**

**Advantages**
- It is efficient for problems with a large number of nodes.
**Disadvantages**
- Not [[Optimal Algorithm| optimal]]. It is not guaranteed to find the best solution.
- Not [[Complete Algorithm]]. Due to its greedy nature, it may get stuck in an infinite loop.
### GBFS Simulation
![[gbfs.png]]
