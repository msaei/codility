## Lesson9: Maximum slice problem
## MaxSliceSum
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_slice_sum/)

###solution for Python(100-100)
```
def solution(A):
    # write your code in Python 3.6
    current_slice = A[0]
    best_slice = A[0]
    for i in range(1,len(A)):
        if current_slice <= 0:
            current_slice = A[i]
        else:
            current_slice += A[i]
        best_slice = max(best_slice, current_slice)
    return best_slice
    pass
    
```
