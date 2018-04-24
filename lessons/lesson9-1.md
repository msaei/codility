## Lesson9: Maximum slice problem
## MaxDoubleSliceSum
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_double_slice_sum/)

###solution for python(100-100)
I found it in code says in this link https://codesays.com/2014/solution-to-max-double-slice-sum-by-codility/
```
def solution(A):
    A_len = len(A)    # The length of array A
 
    # Get the sum of maximum subarray, which ends this position
    # Method: http://en.wikipedia.org/wiki/Maximum_subarray_problem
    max_ending_here = [0] * A_len
    max_ending_here_temp = 0
    for index in range(1, A_len-2):
        max_ending_here_temp = max(0, A[index]+max_ending_here_temp)
        max_ending_here[index] = max_ending_here_temp
 
    # Get the sum of maximum subarray, which begins this position
    # The same method. But we travel from the tail to the head
    max_beginning_here = [0] * A_len
    max_beginning_here_temp = 0
    for index in range(A_len-2, 1, -1):
        max_beginning_here_temp = max(0, A[index]+max_beginning_here_temp)
        max_beginning_here[index] = max_beginning_here_temp
 
    # Connect two subarray for a double_slice. If the first subarray
    # ends at position i, the second subarray starts at position i+2.
    # Then we compare each double slice to get the one with the
    # greatest sum.
    max_double_slice = 0
    for index in range(0, A_len-2):
        max_double_slice = max(max_double_slice,
                 max_ending_here[index] + max_beginning_here[index+2] )
 
    return max_double_slice
    pass
    
```
### python(92)
my solution does not work for one of test case
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
