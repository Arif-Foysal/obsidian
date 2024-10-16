<iframe width="560" height="315" src="https://www.youtube.com/embed/tvNNKorAWog?si=UYGpczKOyhsyDoFg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


The **Northwest Corner Method** is a technique used for finding an initial feasible solution to a transportation problem. This method follows a systematic approach starting from the top left (northwest) corner of the cost matrix and moving towards the southeast corner. Let's apply the Northwest Corner Method to the given problem.
![[Pasted image 20241017022720.png]]
**Sol:**
### Initial Setup and Cost Table
The problem is **Balanced Transportation Problem**.
We have three warehouses (A, B, C) and four stores (1, 2, 3, 4). The transportation cost per unit between each warehouse and store, the supply at each warehouse, and the demand at each store are as follows:

$$
\begin{array}{|c|c|c|c|c|c|}
\hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
\hline \text{Warehouse A} & 8 & 6 & 10 & 9 & 20 \\
\hline \text{Warehouse B} & 9 & 12 & 13 & 7 & 25 \\
\hline \text{Warehouse C} & 14 & 9 & 16 & 5 & 30 \\
\hline \text{Demand (units):} & 25 & 10 & 15 & 25 & \\
\hline
\end{array}
$$

### Step-by-Step Allocation Using Northwest Corner Method

1. **Start at the Northwest Corner (Warehouse A to Store 1):**
   - Allocate \(\min(20, 25) = 20\) units.
$$
   \begin{array}{|c|c|c|c|c|c|}
   \hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
   \hline \text{Warehouse A} & 20 & 0 & 0 & 0 & 0 \\
   \hline \text{Warehouse B} & & & & & 25 \\
   \hline \text{Warehouse C} & & & & & 30 \\
   \hline \text{Demand:} & 5 & 10 & 15 & 25 & \\
   \hline
   \end{array}
$$

2. **Move to Warehouse B (since Warehouse A's supply is exhausted):**
   - **Warehouse B to Store 1**: Allocate \(\min(5, 25) = 5\) units.
$$
   \begin{array}{|c|c|c|c|c|c|}
   \hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
   \hline \text{Warehouse A} & 20 & 0 & 0 & 0 & 0 \\
   \hline \text{Warehouse B} & 5 & 0 & 0 & 0 & 20 \\
   \hline \text{Warehouse C} & & & & & 30 \\
   \hline \text{Demand:} & 0 & 10 & 15 & 25 & \\
   \hline
   \end{array}
$$

3. **Next, Warehouse B to Store 2:**
   - Allocate \(\min(10, 20) = 10\) units.
$$
   \begin{array}{|c|c|c|c|c|c|}
   \hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
   \hline \text{Warehouse A} & 20 & 0 & 0 & 0 & 0 \\
   \hline \text{Warehouse B} & 5 & 10 & 0 & 0 & 10 \\
   \hline \text{Warehouse C} & & & & & 30 \\
   \hline \text{Demand:} & 0 & 0 & 15 & 25 & \\
   \hline
   \end{array}
$$

4. **Next, Warehouse B to Store 3:**
   - Allocate \(\min(15, 10) = 10\) units.
$$
   \begin{array}{|c|c|c|c|c|c|}
   \hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
   \hline \text{Warehouse A} & 20 & 0 & 0 & 0 & 0 \\
   \hline \text{Warehouse B} & 5 & 10 & 10 & 0 & 0 \\
   \hline \text{Warehouse C} & & & 5 & & 30 \\
   \hline \text{Demand:} & 0 & 0 & 0 & 25 & \\
   \hline
   \end{array}
$$

5. **Next, Warehouse C to Store 3:**
   - Allocate \(\min(15, 30) = 5\) units.
$$
   \begin{array}{|c|c|c|c|c|c|}
   \hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
   \hline \text{Warehouse A} & 20 & 0 & 0 & 0 & 0 \\
   \hline \text{Warehouse B} & 5 & 10 & 10 & 0 & 0 \\
   \hline \text{Warehouse C} & 0 & 0 & 5 & 25 & 0 \\
   \hline \text{Demand:} & 0 & 0 & 0 & 0 & \\
   \hline
   \end{array}
$$

6. **Last, Warehouse C to Store 4:**
   - Allocate the remaining 25 units.

### Cost Calculation
Now, let's calculate the total transportation cost using these allocations:

$$
\begin{array}{|c|c|c|c|c|c|}
\hline & \text{Store 1} & \text{Store 2} & \text{Store 3} & \text{Store 4} & \text{Supply} \\
\hline \text{Warehouse A} & 20 \times 8 & 0 & 0 & 0 & 0 \\
\hline \text{Warehouse B} & 5 \times 9 & 10 \times 12 & 10 \times 13 & 0 & 0 \\
\hline \text{Warehouse C} & 0 & 0 & 5 \times 16 & 25 \times 5 & 0 \\
\hline \text{Demand:} & & & & & \\
\hline \end{array}
$$

$$
\text{Total Cost} = (20 \times 8) + (5 \times 9) + (10 \times 12) + (10 \times 13) + (5 \times 16) + (25 \times 5)
$$

Calculating:
$$
= 160 + 45 + 120 + 130 + 80 + 125
$$
$$
= 660
$$

$$\boxed{660}$$

Thus, the total transportation cost using the Northwest Corner Method is $660, which confirms the total cost provided in the example.