#artificial-intellegence #Algorithm 

**Objective**
we have to place 8 queens in 8x8 chess board in a way such that no queen can attack each other.
In [[chess]], a queen can move horizontally, vertically, and diagonally across the board. The goal is to find a placement where no two queens share the same row, column, or diagonal.


## Problem Formulation

### State
A configuration of 8 queens on the board so that only one queen placed on each column.

### Size of State Space 
Size of state space will be, $$8^8=17 Million$$Because there are 8 possible configurations for each columns.
### Goal Test
We have to make sure that we have reached a state where no queen is threatened by another.
