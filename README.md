# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![exp 8 step 2](https://github.com/Safeeq-Fazil/QRdecomposition/assets/118680361/512d0a8b-ab04-4da9-91af-2448d56ac733)

3.	Obtain the Q matrix   
![exp 8 step 3](https://github.com/Safeeq-Fazil/QRdecomposition/assets/118680361/10f58df0-6e84-40c9-a08c-6e3129852d12)

4.	Construct the upper triangular matrix R
![exp 8 step 4](https://github.com/Safeeq-Fazil/QRdecomposition/assets/118680361/819de1a1-7f48-498f-98a9-4981d0884757)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Safeeq Fazil.A
RegisterNumber: 212222240086
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    Q= np.empty((n,n))
    u = np.empty((n,n))
    
    u[:, 0]= A[:, 0]
    Q[:, 0]= u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1,n):
        
        u[:, i]=A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
            
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i, m):
            R[i,j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
    
    
    
a = np.array(eval(input()))
QR_Decomposition(a)





```

## Output
![qr ](https://github.com/Safeeq-Fazil/QRdecomposition/assets/118680361/2a24244b-a603-49b2-90b3-faaf62f88c6a)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
