## [[K-Means Clustering]]

### Problem:
Classify the following data points into two clusters using the K-means algorithm: (3,4), (6,7), (4,5), (5,7), (2,6)

### Solution

#### 📌 **Given Data Points**:

- A = (3, 4)
- B = (6, 7)
- C = (4, 5)
- D = (5, 7)
- E = (2, 6)
We want to classify them into **2 clusters (K = 2)** using the **K-Means algorithm**

#### **Step 1: Choose Initial Centroids**

Let’s **randomly choose**:

- **Centroid 1 (C1)** = A = (3, 4)
- **Centroid 2 (C2)** = B = (6, 7)
#### **Step 2: Assign Each Point to the Nearest Centroid**

We’ll calculate the **Euclidean distance** between each point and both centroids:

#### Distance formula:

$$d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$$

| Point   | Distance to C1 (3,4) | Distance to C2 (6,7) | Assigned Cluster |
| ------- | -------------------- | -------------------- | ---------------- |
| A (3,4) | 0.0                  | √18 ≈ 4.24           | C1               |
| B (6,7) | √18 ≈ 4.24           | 0.0                  | C2               |
| C (4,5) | √2 ≈ 1.41            | √5 ≈ 2.24            | C1               |
| D (5,7) | √13 ≈ 3.61           | √1 = 1.0             | C2               |
| E (2,6) | √5 ≈ 2.24            | √17 ≈ 4.12           | C1               |

#### ✅ Cluster Assignments:

- **Cluster 1 (C1)**: A, C, E
- **Cluster 2 (C2)**: B, D

#### 🔄 **Step 3: Recalculate the Centroids**

#### For Cluster 1 (A, C, E):
Points: (3,4), (4,5), (2,6)  
New Centroid:

$$x = \frac{3+4+2}{3} = 3,\quad y = \frac{4+5+6}{3} = 5 \Rightarrow \text{New C1} = (3, 5)$$

### For Cluster 2 (B, D):

Points: (6,7), (5,7)  
New Centroid:

x=(6+5)/2 = 5.5
y= (7+7)/2 = 7

Now run more iterations until centroids stablizes, and finally stop the algorithm

## [[Modified K-Means Clustering]]

<iframe width="560" height="315" src="https://www.youtube.com/embed/oQ5yRkoBN0M?si=HfSU7r7fORmv2CU2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


### Problem:
Classify the following data points into two clusters using the **Modified** K-means algorithm: (3,4), (6,7), (4,5), (5,7), (2,6)


![[Screenshot 2025-04-11 at 12.44.16 AM.png]]



### **Why do we need modified k-means clustering algorithm?**

Modified K-Means, such as K-Means++, is needed because standard K-Means selects initial centroids randomly, which can lead to poor clustering, slow convergence, and inconsistent results. This randomness often causes the algorithm to get stuck in local minima or produce inaccurate clusters. K-Means++ improves this by choosing the initial centroids more intelligently—spreading them out based on distances—which leads to better accuracy, faster convergence, and more stable results. By starting with well-placed centroids, modified K-Means ensures more reliable performance, especially on complex datasets.

