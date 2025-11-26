# EX 6B KNAPSACK PROBLEM
## DATE:29-10-2025
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1.Goal: Two robots start at the top row—one at the leftmost and one at the rightmost column—and move down to collect the maximum number of cherries. If both visit the same cell, count the cherry only once.

2.Function dp(i, j, k): Recursively calculates the maximum cherries that can be collected from row i, with robot 1 at column j and robot 2 at column k.

3.Memoization: The memo dictionary is used to store and reuse already computed results for the same (i, j, k) state to avoid repeated work.

4.Choices: Each robot can move left, right, or stay in the same column for the next row, giving 9 combinations in total (3 x 3 loop).

5.Final Output: The result of obj.cherryPickup(grid) is added to 3 (+3) in the print line, which might be an extra value manually added for a specific purpose (not from the logic itself).

## Program:
```
To implement the program for 0/1 knapsack problem.
Developed by: RIZWAN T
Register Number:  212222040134

```
```python
def knapSack(W, wt, val, n):
    K = [[0 for x in range(W + 1)] for x in range(n + 1)]
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                K[i][w] = 0
            elif wt[i-1] <= w:
                K[i][w] = max(val[i-1]+ K[i-1][w-wt[i-1]],K[i-1][w])
            else:
                K[i][w] = K[i-1][w]
 
    return K[n][W]

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```
## Output:


![image](https://github.com/user-attachments/assets/0942b627-6b9b-4b30-9f60-3582b5512130)

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
