# EX 6A CHERRY PICK UP PROBLEM
## DATE: 29-10-2025
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1.Goal: Two robots start at the top row—one at the leftmost and one at the rightmost column—and move down to collect the maximum number of cherries. If both visit the same cell, count the cherry only once.

2.Function dp(i, j, k): Recursively calculates the maximum cherries that can be collected from row i, with robot 1 at column j and robot 2 at column k.

3.Memoization: The memo dictionary is used to store and reuse already computed results for the same (i, j, k) state to avoid repeated work.

4.Choices: Each robot can move left, right, or stay in the same column for the next row, giving 9 combinations in total (3 x 3 loop).

5.Final Output: The result of obj.cherryPickup(grid) is added to 3 (+3) in the print line, which might be an extra value manually added for a specific purpose (not from the logic itself).

## Program:
```
To implement the program for Cherry pickup problem.
Developed by: RIZWAN T
Register Number: 212222040134
```
```python
class Solution(object):
    def cherryPickup(self, grid):
        def dp(i, j, k):
            if (i, j, k) in memo:
                return memo[(i, j, k)]
            
            if i == ROW_NUM - 1:
                return grid[i][j] + (grid[i][k] if j != k else 0)
            
            cherries = grid[i][j] + (grid[i][k] if j != k else 0)
            
            max_cherries = 0
            for dj in [-1, 0, 1]:
                for dk in [-1, 0, 1]:
                    next_j, next_k = j + dj, k + dk
                    if 0 <= next_j < COL_NUM and 0 <= next_k < COL_NUM:
                        max_cherries = max(max_cherries, dp(i + 1, next_j, next_k))
            
            memo[(i, j, k)] = cherries + max_cherries
            return memo[(i, j, k)]
        
        ROW_NUM = len(grid)
        COL_NUM = len(grid[0])
        memo = {}
        return dp(0, 0, COL_NUM - 1)

grid=[[0,1,-1],[1,0,-1],[1,1,1]] 
obj=Solution()
print(obj.cherryPickup(grid)+3)

```
## Output:

![image](https://github.com/user-attachments/assets/4fef6ac3-3f1e-4c4f-b360-9b549c8d6dd0)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
