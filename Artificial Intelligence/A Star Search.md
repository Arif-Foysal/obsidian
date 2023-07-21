#Computer-Science #artificial-intellegence #Algorithm #GreedyAlgorithm  

A* (pronounced as "A star") is a popular and widely used graph traversal algorithm in computer science and artificial intelligence. It is a [[Informed search algorithm]] that used for finding the shortest path between two nodes in a weighted graph, where each edge has a non-negative cost. The A* algorithm is designed to be both [[Complete Algorithm|complete]] (finds a solution if one exists) and [[Optimal Algorithm|optimal]] (finds the shortest path).
> A* search is a combination of [[Uniform Cost Search(UCS)]] and [[Greedy Breadth-First Search(GBFS)]]

It uses a [[Heuristic Function]], often denoted as h(n), to estimate the cost of reaching the goal node from a given node. The heuristic function is essential in guiding the search towards the goal efficiently.`

## Features of A* search

### Advantages
- A* search is a  [[Optimal Algorithm]]. But it must be fed with an [[Admissible Heuristic]]. It may not find the optimal path if it is fed with a bad heuristic function.
>[!Note]
>[[A star tree search]] will be optimal if fed with [[Admissible Heuristic]].
>[[A Star Graph Search]] may not find optimal solution even if fed with [[Admissible Heuristic]].



### Disadvantages
- 
#### How does a bad heuristic function affect optimality of A* search


## A* Search Heuristic Function
![[A Star heuristic funciton.svg]]
## A* Search Simulation

### [[A star tree search]] Simulation:

![[A star graph 01.svg]]
Here, 
	**Start State:** S
	**Goal State:** G



### [[A Star Graph Search]] Simulation:

