# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the necessary libraries and get input from the user
2.Use nested loops to iterate over each element of the matrix
3.Perform Gaussian elimination to solve the system of linear equations.
4.Use back Substitution and Print the output
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:DHARSHAN PT
RegisterNumber:23005803 
*/
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by:DHARSHAN PT
RegisterNumber:23005803 
'''
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit('Divide by zero detected!')
    
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')

## Output:
![Screenshot 2024-01-01 233403](https://github.com/dharshanpt/Gaussian/assets/138849376/b5df0c80-a2a1-45ee-a2fe-19bd4d7a2c15)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

