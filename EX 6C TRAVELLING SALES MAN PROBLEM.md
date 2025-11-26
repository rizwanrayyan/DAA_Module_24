# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:29-10-2025
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1.Goal: Find the shortest possible route that visits every city exactly once and returns to the starting city (s).

2.: A 2D list graph represents the distances between cities. V = 4 means there are 4 cities.

3.Permutations: The code generates all possible orders of visiting the other cities (excluding the start city s) using itertools.permutations.

4.Path Calculation: For each city order, it calculates the total distance starting from s, visiting each city in the order, and returning to s.

5.Result: The minimum total path length from all possible routes is stored in min_path and returned as the solution.
## Program:
```
To implement the program for TSP.
Developed by: RIZWAN T
Register Number: 212222040134
```
```python
from sys import maxsize
from itertools import permutations
V = 4
 

def travellingSalesmanProblem(graph, s):
    vertex = [] 
    for i in range(V): 
        if i != s: 
            vertex.append(i) 
    min_path = maxsize 
    next_permutation=permutations(vertex)
    for i in next_permutation:

        current_pathweight = 0
        k = s 
        for j in i: 
            current_pathweight += graph[k][j] 
            k = j 
        current_pathweight += graph[k][s] 
        min_path = min(min_path, current_pathweight) 
         
    return min_path
   
 
 

if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:

![image](https://github.com/user-attachments/assets/6fdc1e59-bf52-424b-914a-ca30d14f174e)


## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
