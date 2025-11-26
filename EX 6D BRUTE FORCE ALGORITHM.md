# EX 6D BRUTE FORCE ALGORITHM
## DATE:29-10-2025
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.




## Algorithm
1.Goal: Find and print all starting indices where the substring sub appears in the main string string.

2.Inputs: The user is asked to input two strings — str1 (main string) and str2 (substring to search).

3.Looping: The code checks each possible position in string where sub could fit (l - ls + 1 positions).

4.Matching: At each position, it slices the main string and compares it with sub. If they match, it prints the index.

5.Output: If a match is found, it prints "Found at index <i>" for each occurrence.

## Program:
```
To implement the program using brute force method of searching for the given substring in the main string.
Developed by: RIZWAN T
Register Number: 212222040134
```

```python
def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]
    for i in range(l-ls+1):
        if string[i:i+ls]==sub:
            print(f"Found at index {i}")

str1=input()
str2=input()
```

## Output:

![image](https://github.com/user-attachments/assets/88091181-1762-4c24-bddd-6f7784c04466)


## Result:
Thus the above program was executed successfully for searching the substring at respective index.
