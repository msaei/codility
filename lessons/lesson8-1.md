## Lesson 8: Leader
## Dominator
link to question: (https://app.codility.com/programmers/lessons/8-leader/dominator/)

### solution for python
```
def solution(A):
    # write your code in Python 3.6
    counter = 0
    
    B = A[:]
    B.sort()
    candid = B[len(B)//2]
    for i in range(len(A)):
        if A[i] == candid:
            counter = counter + 1
    if counter > len(A)//2:
        return A.index(candid)
    return -1
    
    pass
    
```
