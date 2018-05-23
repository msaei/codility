## Lesson 13: Fibonacci numbers
## Ladder
link to question: (https://app.codility.com/programmers/lessons/13-fibonacci_numbers/ladder/)  

### solution for python(100-75)
performance detail (https://app.codility.com/demo/results/trainingXETK2D-QDD/)
```
# you can write to stdout for debugging purposes, e.g.
# print("this is a debug message")

def solution(A, B):
    # write your code in Python 3.6
    N = len(A)
    result = [0] * N
    fib = fibonacci(N + 1)
    for i in range(0, N):
        result[i] = fib[A[i] + 1] % (2 ** B[i])
    return result
    pass

def fibonacci(n):
    fib = [0] * (n + 1)
    fib[1] = 1
    for i in range(2, n + 1):
    
```
