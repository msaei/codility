## Lesson 8: Leader
## EquiLeader
link to question: (https://app.codility.com/programmers/lessons/8-leader/equi_leader/)
### solution for python
```
def getLeader(A):
    # write your code in Python 3.6
    
    if len(A) < 2:
        return len(A) - 1
    counter = 0
    
    B = A[:]
    B.sort()
    candid = B[len(B)//2]
    for i in range(len(A)):
        if A[i] == candid:
            counter = counter + 1
    if counter > len(A)//2:
        return candid
    return None
    
    pass
```
