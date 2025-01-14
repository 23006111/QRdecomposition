# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given
3.	
	![image](https://github.com/23006111/QRdecomposition/assets/145981696/9ddd831d-526a-4715-b079-faa52bb490f5)
   


 Obtain the Q matrix
   Q = (e1|e2| ... ... ...en)
  
    



4.	Construct the upper triangular matrix R
	![image](https://github.com/23006111/QRdecomposition/assets/145981696/19742fc4-d564-4005-ac52-ff33bf6f3b27)

    



## Program:
### Gram-Schmidt Method
~~~
Program to QR decomposition using the Gram-Schmidt method
Developed by: RAMYA P
RegisterNumber: 23006111

import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i] @ Q[:,j]) * Q[:, j]
            Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@ Q[:,i]
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)
~~~









## Output
![image](https://github.com/23006111/QRdecomposition/assets/145981696/588fdb7e-cdd7-450a-9800-c8c533290c30)




## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
