## Lesson 8: Leader
## EquiLeader
link to question: (https://app.codility.com/programmers/lessons/8-leader/equi_leader/)
### solution for python
```
def getCountOf(B, leader):
    count = 0
    for el in B:
        if el == leader:
            count += 1
    return count
        
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    B = A[:]
    B.sort()
    leader = B[int(N/2)]
    M = getCountOf(B, leader)
    firstLen = 0
    secLen = N
    leaderCount = 0
    result = 0
    for num in A:
        firstLen += 1
        secLen -= 1
        if secLen == 0:
            break
        if num == leader:
            leaderCount += 1
        if (leaderCount/firstLen>0.5) and ((M - leaderCount)/secLen)>0.5:
            result += 1

    return result
    pass
```
