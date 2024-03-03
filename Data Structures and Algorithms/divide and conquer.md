#programming #Algorithm #divide-and-conquer

[[longest common prefix]]
[[count inversions]]
[[merge sort]]
[[d and c lab]]

This technique can be divided into the following three parts:

1. **Divide:** This involves dividing the problem into smaller sub-problems.
2. **Conquer:** Solve sub-problems by calling recursively until solved.
3. **Combine:** Combine the sub-problems to get the final solution of the whole problem.  
     

The following are some standard algorithms that follow Divide and Conquer algorithm.  

1. [**Quicksort**](https://www.geeksforgeeks.org/quick-sort/) is a sorting algorithm. The algorithm picks a pivot element and rearranges the array elements so that all elements smaller than the picked pivot element move to the left side of the pivot, and all greater elements move to the right side. Finally, the algorithm recursively sorts the subarrays on the left and right of the pivot element.
2. [[merge sort]] is also a sorting algorithm. The algorithm divides the array into two halves, recursively sorts them, and finally merges the two sorted halves.
3. [**Closest Pair of Points**](https://www.geeksforgeeks.org/closest-pair-of-points-using-divide-and-conquer-algorithm/) The problem is to find the closest pair of points in a set of points in the x-y plane. The problem can be solved in O(n^2) time by calculating the distances of every pair of points and comparing the distances to find the minimum. The Divide and Conquer algorithm solves the problem in O(N log N) time.
4. [**Strassen’s Algorithm**](https://www.geeksforgeeks.org/strassens-matrix-multiplication/) is an efficient algorithm to multiply two matrices. A simple method to multiply two matrices needs 3 nested loops and is O(n^3). Strassen’s algorithm multiplies two matrices in O(n^2.8974) time.
5. [**Cooley–Tukey Fast Fourier Transform (FFT) algorithm**](http://en.wikipedia.org/wiki/Cooley%E2%80%93Tukey_FFT_algorithm) is the most common algorithm for FFT. It is a divide and conquer algorithm which works in O(N log N) time.
6. [**Karatsuba algorithm for fast multiplication**](https://www.geeksforgeeks.org/karatsuba-algorithm-for-fast-multiplication-using-divide-and-conquer-algorithm/) does the multiplication of two _n_-digit numbers in at most
