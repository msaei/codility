## Lesson 14: Binary search algorithm
## NailingPlanks
link to question: (https://app.codility.com/programmers/lessons/14-binary_search_algorithm/nailing_planks/)
### solution for python(62-100-25)
performance detail:(https://app.codility.com/demo/results/trainingT7PKKB-HHY/)
```
def solution(A, B, C):
    # write your code in Python 3.6
    for i in range(len(C)):
        nail_pos = C[i]
        A, B = remove_nailed_planks(nail_pos, A, B)
        if len(A) == 0:
            return i + 1
    return -1
    pass

def remove_nailed_planks(nail_pos, A, B):
    Edited_A = []
    Edited_B = []
    for i in range(len(A)):
        if nail_pos < A[i] or nail_pos > B[i]:
            #the plank is not under nail
            Edited_A.append(A[i])
            Edited_B.append(B[i])
    return Edited_A, Edited_B
    pass
    
```
