# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:16/5/25
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm.   
1.Input String: The function takes a single string seq and calculates its longest palindromic subsequence.

2.Dynamic Programming Table: A 2D table df is created to store the results of subproblems for optimized computation (memoization).

3.Recursive Function: The function lps is defined recursively to find the longest common subsequence (LCS) between the original string and its reverse.

4.Base Case: If either string has length 0, the LPS length is 0.

5.Memoization: The function stores results in df to avoid redundant calculations, returning the final LPS length at the end.
## Program:
```
Program to implement to find the length of the longest palindromic subsequence in it
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
df=[[-1 for i in range(1001)]for j in range(1001)]
def lps(s1,s2,n1,n2):
    if(n1==0 or n2==0):
        return 0
    if(df[n1][n2]!=-1):
        return df[n1][n2]
    if (s1[n1-1]==s2[n2-1]):
        df[n1][n2]=1+lps(s1,s2,n1-1,n2-1)
        return df[n1][n2]
    else:
        df[n1][n2]=max(lps(s1,s2,n1-1,n2),lps(s1,s2,n1,n2-1))
        return df[n1][n2]
seq=input()
n=len(seq)
s2=seq
s2=s2[::-1]
print('The length of the LPS is',lps(s2,seq,n,n))
```

## Output:

![image](https://github.com/user-attachments/assets/281e7d2b-4995-497c-990d-12a78cc00e1e)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
