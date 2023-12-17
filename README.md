# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the numpy module to use the built -in functions for calculation.
2.import the sys module to use the built-in functions.
3.Get input from the user for number of rows and add it by 1 for number of coloumns.
4.using np.zeros() set the matrix as null matrix.
5.Using nested for loop get input from the user for each element in the matrix
6.using nested for loop find the ratio and perform the elementary row operations and find matrix
7.use back substitution method to find the value of the variables and print it.
8.End the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: RAJARAMAN V
RegisterNumber: 23014299
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
X[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i]=a[i][n]
    for j in range(i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
    X[i]=X[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,X[i]),end=" ")
```

## Output:
![image](https://github.com/Rajaraman77/Gaussian/assets/150319383/b5c55371-7c69-4dd1-bc90-9e1f49163a80)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

