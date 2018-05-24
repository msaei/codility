## Lesson 13: Fibonacci numbers
## Ladder
link to question: (https://app.codility.com/programmers/lessons/13-fibonacci_numbers/ladder/)  

### solution for python(100-75)
performance detail (https://app.codility.com/demo/results/trainingXETK2D-QDD/)
I dont get why is the time O[L**2] ???
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

### solution I found in codesays(100-100)
different way to calculate modulo and power of 2 with bit manupulating (useng shift << and &)
performance detail (https://app.codility.com/demo/results/trainingH6KJJE-HUA/)  
code says link (https://codesays.com/2014/solution-to-ladder-by-codility/)
```
def solution(A, B):
    limit = len(A)                  # The possible largest N rungs
    result = [0] * len(A)           # The result for each query
    B = [(1<<item)-1 for item in B] # Pre-compute B for optimization
 
    # Compute the Fibonacci numbers for later use
    fib = [0] * (limit+2)
    fib[1] = 1
    for i in range(2, limit + 2):
        fib[i] = fib[i - 1] + fib[i - 2]
 
    for i in range(limit):
        # To climb to A[i] rungs, you could either
        # come from A[i]-1 with an one-step jump
        # OR come from A[i]-2 with a two-step jump
        # So from A[i] rungs, the number of different ways of climbing
        # to the top of the ladder is the Fibonacci number at position
        # A[i] + 1
        result[i] = fib[A[i]+1] & B[i]
 ```
