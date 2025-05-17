
# Manhattan K-Means Clustering (2D Grid Visualization)

This Python program performs **K-Means clustering** using **Manhattan distance** on 2D points and provides a simple **text-based grid visualization**.

## 📌 Description

* **Points**: 100 random 2D points (in a 50x50 grid).
* **Centers**: 10 random initial cluster centers.
* **Distance Metric**: Manhattan distance (`|x1 - x2| + |y1 - y2|`).
* **Clustering**: Iteratively assigns points to nearest center and updates centers until convergence.
* **Visualization**: Prints a 50x50 grid:

  * `'P'` = Point
  * `'C'` = Cluster center
  * `'.'` = Empty space





## 🧠 Key Functions

* `manhattan_distance(a, b)`: Computes Manhattan distance.
* `kmeans_manhattan(points, centers, max_iter)`: Runs the K-Means algorithm.
* `visualize(points, centers)`: Displays the final clusters in a grid.

## ✅ Sample Output

```
2D Visualization of Clustered Data (Manhattan K-Means):
(P = Data Point, C = Cluster Center)
. . . . . . . P . . . . C . . . . . . . .
...
```

## 📦 Requirements

* `numpy` (used for array operations)

---

Let me know if you'd like this formatted or saved to a file!

[image](https://github.com/user-attachments/assets/f8de5f46-0da1-4458-831d-cece7ecb9a70)
