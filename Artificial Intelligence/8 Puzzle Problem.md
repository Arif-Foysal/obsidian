#Algorithm #GreedyAlgorithm #Computer-Science #artificial-intellegence 

![[8puzzle 01.svg]]
## Problem Formulation

### What are the states?
All positions of the 3x3 grid
### How many states?
The [[State space]] in the 8-puzzle problem consists of all possible configurations of the 3x3 grid with the eight numbered tiles and one empty space.
Here,
There are 9 positions on the 3x3 grid, and each position can be occupied by one of the 8 tiles (numbers 1 to 8) or left empty (represented by 0). So, there are 9 choices for the first position, 8 choices for the second position, 7 choices for the third position, and so on until the last position, which has only one choice. The total number of possible initial configurations is 9! ([[Factorial]] of 9)
But half of the configurations aren't possible to reach from any chosen starting point. So we divide total configurations by 2 to get the total number of states that can move step by step to the solution.
So, the **total number of states** in 8-puzzle problem:
$$\frac{9!}{2}$$
### What are the actions
- Moving the blank space **Left, Right, Up and Down** 
### How many successor from the start rule?

### What should the cost be
The cost of  moving every tile is equal. So let's consider it 1.

## Heuristic Function
**Number of misplaced tiles** can be a [[Admissible Heuristic]] function. Because it would at least take **Number of misplaced tiles** steps to slide them into their correct position.
For our particular problem, we have got all 8 of the tiles misplaced.
So, it would take at least 8 steps to correct them.
>That is why our [[Heuristic Function|heuristic]] can be 8 for our given problem.

