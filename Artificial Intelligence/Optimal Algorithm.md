#Algorithm #artificial-intellegence #Computer-Science 

An optimal algorithm is one that is guaranteed to find the best solution with the **minimum cost or shortest path** among all possible solutions in the search space. In the context of pathfinding algorithms, an optimal algorithm finds the shortest path between a starting node and a goal node with the lowest possible cost.
For example, the Dijkstra's algorithm is an optimal algorithm for finding the shortest path in a weighted graph when all edge weights are non-negative. It guarantees finding the shortest path, but it may not be the most efficient algorithm in terms of time and space complexity, especially when there are negative edge weights.

>It's worth noting that the properties of [[Complete Algorithm|completeness]] and [[Optimal Algorithm|optimality]] are independent of each other. An algorithm can be complete without being optimal (e.g., BFS), and it can be optimal without being complete (e.g., [[A Star Search]] with an admissible heuristic, which can fail to find a solution in certain cases).


