#Computer-Science #artificial-intellegence #Algorithm #GreedyAlgorithm 

A [[Heuristic Function]] is consistent if **heuristic arc cost** do not overestimate actual **arc cost**. 

![[consistent-heuristic 01.svg]]
Here,
Arc cost from A to C,
	`cost(A,C)=1`
Heuristic arc cost from A to C,
	`h(A)-h(C)`
In order for the heuristic to be consistent,
	`h(A)-h(C) <= cost(A,C)`

>All consistent heuristics are [[Admissible Heuristic|Admissible]], but all admissible heuristics are consistent.



