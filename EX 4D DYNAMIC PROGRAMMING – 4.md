# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:16/5/25
## AIM:
Create a Naive recursive python program to find the minimum number of operations to convert str1 to str2


## Algorithm
1.Base Cases: The function handles the case where one of the strings is empty by returning the length of the other string.

2.Recursive Approach: If the characters of the two strings match, the function recursively checks the remaining substrings.

3.Edit Operations: If the characters do not match, the function considers three possible edit operations: insertion, deletion, and substitution.

4.Minimization: It returns the minimum number of operations (insertion, deletion, substitution) required to convert one string into another.

5.Time Complexity: The function uses recursion, which can be improved by memoization to avoid recalculating the same subproblems.

## Program:
```
/*
Naive recursive python program to find the minimum number of operations to convert str1 to str2
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def edit_distance(str1, str2, a, b):
    if a==0:
        return b
    if b==0:
        return a
    if str1[a-1]==str2[b-1]:
        return edit_distance(str1,str2,a-1,b-1)
    return 1+min(edit_distance(str1,str2,a,b-1),edit_distance(str1,str2,a-1,b),edit_distance(str1,str2,a-1,b-1))
str1=input()
str2=input()
print("Edit Distance",edit_distance(str1,str2,len(str1),len(str2)))
```

## Output:


![image](https://github.com/user-attachments/assets/6ae50911-991a-483e-bd5b-b1e77c35e503)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
