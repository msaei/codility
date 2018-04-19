## Lesson9: Maximum slice problem
## MaxProfit
link to question:(https://app.codility.com/programmers/lessons/9-maximum_slice_problem/max_profit/)

###solution for python(50)
```
def solution(A):
    # write your code in Python 3.6
    buy = A[0]
    sel = A[-1]
    profit = 0
    for i in range(1, len(A)):
        if A[i] < buy:
            buy = A[i]
        else:
            sel = A[i]
        profit = max(0, profit, (sel - buy))
        
    return profit
        
    pas
    
```
