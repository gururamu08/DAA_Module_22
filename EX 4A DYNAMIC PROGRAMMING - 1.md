# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:16/5/25
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
1.Input Strings: The function takes two strings u and v as input.

2.Initialize Table: It creates a 2D table c to store the lengths of LCS at each position.

3.Fill Table: The table is filled using dynamic programming, where each cell c[i][j] represents the length of LCS for substrings u[i:] and v[j:].

4.Construct LCS: The function print_lcs reconstructs and prints one of the LCS from the table.

5.Result: The longest common subsequence is printed as output.
## Program:
```
Program to implement the longest common subsequence using Dynamic Programming
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def lcs(u, v):
    """Return c where c[i][j] contains length of LCS of u[i:] and v[j:]."""
    c = [[-1]*(len(v) + 1) for _ in range(len(u) + 1)]
    for i in range(len(u) + 1):
        c[i][len(v)] = 0
    for j in range(len(v)):
        c[len(u)][j] = 0
 
    for i in range(len(u) - 1, -1, -1):
        for j in range(len(v) - 1, -1, -1):
            if u[i] == v[j]:
                c[i][j] = 1 + c[i + 1][j + 1]
            else:
                c[i][j] = max(c[i + 1][j], c[i][j + 1])
    return c
 
def print_lcs(u, v, c):
    """Print one LCS of u and v using table c."""
    i = j = 0
    while not (i == len(u) or j == len(v)):
        if u[i] == v[j]:
            print(u[i], end='')
            i += 1
            j += 1
        elif c[i][j + 1] > c[i + 1][j]:
            j += 1
        else:
            i += 1
 
u = input()
v = input()
c = lcs(u, v)
print_lcs(u, v, c)
```

## Output:

![image](https://github.com/user-attachments/assets/f496aed5-7067-4a05-bc55-58bef93543c9)


## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
