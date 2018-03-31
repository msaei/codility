## Lesson 7: Stacks and Queues
## StoneWall

link to problem: (https://app.codility.com/programmers/lessons/7-stacks_and_queues/stone_wall/)

### solution for python
```
def solution(H):
    # write your code in Python 3.6
    N = 1
    lastHighth = H.pop(-1)
    while (len(H) > 0):
        newHighth = H.pop(-1)
        if ( newHighth != lastHighth):
            N += 1
            lastHighth = newHighth
    return N
    pass
    
```
