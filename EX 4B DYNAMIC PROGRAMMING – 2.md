# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:16/5/25
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
1.Input Strings: The function takes two strings X and Y as input.

2.Dynamic Programming Table: A 2D table LCSuff is created to store the lengths of common substrings between X and Y.

3.Iterate Through Characters: It loops through each character of the two strings, comparing corresponding characters.

4.Track Maximum Length: When a match is found, it updates the table, and keeps track of the maximum length and the ending index of the substring.

5.Return Substring: The longest common substring is extracted and returned based on the maximum length found.  

## Program:
```
Program to implement the longest common substring problem
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def LCSubStr(X,Y,m,n):
    maxLength = 0           # stores the max length of LCS
    endingIndex = m 
    LCSuff=[[0 for k in range(n+1)]for l in range(m+1)]
    #result=0
    for i in range(1,m+1):
        for j in range(1,n+1):
            if (X[i-1] == Y[j-1]):
                LCSuff[i][j]=LCSuff[i-1][j-1]+1
                if LCSuff[i][j]>maxLength:
                    maxLength=LCSuff[i][j]
                    endingIndex=i
    return X[endingIndex - maxLength: endingIndex]
X=input()
Y=input()
m=len(X)
n=len(Y)
print('The longest common substring is',LCSubStr(X,Y,m,n))
```

## Output:

![image](https://github.com/user-attachments/assets/22e79269-685d-4723-b055-0efa0adb853f)


## Result:
Thus the program was executed successfully for finding the longest common substring .
