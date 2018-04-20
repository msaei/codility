## Lesson9: Maximum slice problem
## MaxDoubleSliceSum
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_double_slice_sum/)

###solution for python()
```

def solution(A):
    # write your code in Python 3.6
    N = len(A)
    if N < 2:
        return 0

    max_sum = 0
    result = 0
    min_num = A[1]
    for i in range(2, N-1):
        a = A[i]
        if a < min_num:
            max_sum = max(0, max_sum + min_num )
            min_num = a
        else:
            max_sum = max(0, max_sum + a)
            
        result = max(result, max_sum)
    
    return result
    pass
    
```
