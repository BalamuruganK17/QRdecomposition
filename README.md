# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: BALAMURUGAN.K
RegisterNumber: 25017932
'''
import numpy as np
def qr_decomposition(A):
    
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((m,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
          
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)

print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)

```
Question Screenshot: <img width="1451" height="391" alt="Screenshot 2025-11-27 103336" src="https://github.com/user-attachments/assets/5aad0254-13bc-4a68-a4b3-37ad483b46cd" />

Program Screenshot: <img width="1292" height="647" alt="Screenshot 2025-11-27 103323" src="https://github.com/user-attachments/assets/0d80b2f5-2d0f-4ce8-acd1-2b6bef867cf0" />

## Output
```
Screenshot: <img width="1469" height="713" alt="Screenshot 2025-11-27 103239" src="https://github.com/user-attachments/assets/5173aabe-7e6e-4d4e-8abe-4f933688eb5a" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
