#artificial-intellegence #Algorithm 

## Solution
![[n-queens-CSP-01.svg]]
## Formulation 01:
**Variables:** ==Squares on the board==
	$$X_{ij}$$
**Domains:** ==Whether or not a queen is on a specific square.==
	$$\{0,1\}$$
**Constraints:** ==Multiple queens cannot stay on the same row, column or diagonal==
==we need to place n number of queens on the board==
	For row-
	$$\forall i,j,k (X_{ij} , X_{ik})\in\{(0,0),(0,1),(1,0)\}$$
	For column-
	$$\forall i,j,k (X_{ij} , X_{kj})\in\{(0,0),(0,1),(1,0)\}$$
	For Diagonal-
	$$\forall i,j,k (X_{ij} , X_{(i+k)(j+k)}) \in \{(0,0),(0,1),(1,0)\}$$
	$$\forall i,j,k (X_{ij} , X_{(i+k)(j-k)}) \in \{(0,0),(0,1),(1,0)\}$$
	n Number of Queens-
	$$\sum_{i,j}X_{ij}=n$$
	