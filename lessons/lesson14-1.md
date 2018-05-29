## Lesson 14: Binary search algorithm
## NailingPlanks
link to question: (https://app.codility.com/programmers/lessons/14-binary_search_algorithm/nailing_planks/)
### solution for python(0-0)
```
def solution(A, B, C):
    # write your code in Python 3.6
    for i in range(len(C)):
        nail_pos = C[i]
        remove_nailed_planks(nail_pos, A, B)
        if len(A) == 0:
            return i
    return -1
    pass

def remove_nailed_planks(nail_pos, A, B):
    pass
    
```
