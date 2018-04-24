## Lesson9: Maximum slice problem
## MaxDoubleSliceSum
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_double_slice_sum/)

###solution for python(98)

```
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    slice_sum = 0
    result = 0
    min_num = A[1]
    for i in range(2, N-1):
        if slice_sum < 0:
            min_num = A[i]
            slice_sum = 0
            continue
        
        a = A[i]
        if a < min_num:
            slice_sum = slice_sum + min_num
            min_num = a
        else:
            slice_sum = slice_sum + a
            
        result = max(result, slice_sum)
    
    return result
    pass
    
```
### python(92)

```
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    covered_num = A[1]
    slice_sum = 0
    result = 0
    for i in range(2, N - 1):
        
        if A[i] < covered_num:
            slice_sum = slice_sum + covered_num
            covered_num = A[i]
        else:
            slice_sum = slice_sum + A[i]
        if slice_sum <= 0:
            slice_sum = 0
            covered_num = 0
            
        result = max(result, slice_sum)
        
    return result
    pass
```
