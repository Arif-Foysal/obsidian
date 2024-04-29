#Algorithm #Graph 

- [[Yen's k shortest path algorithm]]



<iframe width="560" height="315" src="https://www.youtube.com/embed/EFg3u_E6eHU?si=XVi3cDpwQyl_J7C6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


**Simulator:** https://www.davbyjan.com/
## How it works?

- Set initial distances for all vertices: 0 for the source vertex, and infinity for all the other.
### 2:41
Dijkstra's algorithm repeats a 2-step process:
1. Update Estimates.
2. Choose next node(among unexplored neighbors) mark the vertex as explored.

>**Note:**
>Exploring a vertex gurrantees that we have the shortest path to get to that vertex.

Flaws:
- We only get shortest time to reach a node. We don't get the path through which we have to go.
	- But path can be found by keeping track of what previous node we visited in order to get to this node.
- 
