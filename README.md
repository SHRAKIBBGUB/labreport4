# labreport4
import numpy as np
import random


np.random.seed(42)
points = np.random.randint(0, 50, (100, 2))


centers = np.random.randint(0, 50, (10, 2))

def manhattan_distance(a, b):
    return abs(a[0] - b[0]) + abs(a[1] - b[1])

def kmeans_manhattan(points, centers, max_iter=100):
    for _ in range(max_iter):
        clusters = [[] for _ in range(len(centers))]
        
        
        for point in points:
            distances = [manhattan_distance(point, center) for center in centers]
            closest = np.argmin(distances)
            clusters[closest].append(point)
        
       
        new_centers = []
        for cluster in clusters:
            if cluster:
                new_center = np.mean(cluster, axis=0).astype(int)
                new_centers.append(new_center)
            else:
                new_centers.append(centers[len(new_centers)])  
        
     
        if np.array_equal(centers, new_centers):
            break
        centers = new_centers
    return centers, clusters


final_centers, final_clusters = kmeans_manhattan(points, centers)


def visualize(points, centers, grid_size=50):
    grid = [['.' for _ in range(grid_size)] for _ in range(grid_size)]
    
    
    for cluster in final_clusters:
        for (x, y) in cluster:
            if 0 <= x < grid_size and 0 <= y < grid_size:
                grid[y][x] = 'P'  
    
    
    for (x, y) in final_centers:
        if 0 <= x < grid_size and 0 <= y < grid_size:
            grid[y][x] = 'C' 
    
   
    for row in grid:
        print(' '.join(row))


print("2D Visualization of Clustered Data (Manhattan K-Means):")
print("(P = Data Point, C = Cluster Center)")
visualize(points, final_centers)



[image](https://github.com/user-attachments/assets/f8de5f46-0da1-4458-831d-cece7ecb9a70)
