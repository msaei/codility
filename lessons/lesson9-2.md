## Lesson9: Maximum slice problem
## MaxProfit
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_profit/)

###solution for python(100-100)
```
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    if N < 2:
        return 0
    buy = A[0]
    maxProfit = 0
    for a in A:
        if a < buy:
            buy = a
        
        profit = a - buy
        maxProfit = max(maxProfit, profit, 0)
    return maxProfit
    pass
    
```
