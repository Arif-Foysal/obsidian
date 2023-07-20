#artificial-intellegence #Computer-Science 

>[!contents]
>- [[Uniform Cost Search#Uniform Cost Search Simulation Example|Uniform Cost Search Simulation Example]]
>- 



Uniform-cost search (UCS) is an **uninformed search algorithm** that finds the path with the lowest cumulative cost from the start node to the goal node in a weighted graph. It is an [[Optimal Algorithm]], meaning that it will always find the shortest path to the goal node.

## What is Informed Search Algorithm?

![[Informed search algorithm]]






## Uniform Cost Search Simulation Example

>[!Strategy]
>Expand Cheapest Node First


![[Uniform-cost-search-simulation.jpg]]

### Features of Uniform Cost Search
#### Time and space complexity
The time and space complexity of UCS can be high, especially in graphs with large [[branching factor]]s and many nodes. This is because it considers all possible paths with increasing costs.

**Advantages:**
- [[Complete Algorithm]], Assuming best solution has a finite cost and minimum arc cost is positive, yes!
- It is an [[Optimal Algorithm]], meaning that it will always find the shortest path to the goal node.
- It is efficient, especially for graphs with a large number of nodes.
**Disadvantages:**
- It can be slow for graphs with a large number of edges.
- It can be inefficient for graphs with a high degree of connectivity.