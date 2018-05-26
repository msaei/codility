## Lesson 13: Fibonacci numbers
## FibFrog
link to question:(https://app.codility.com/programmers/lessons/13-fibonacci_numbers/fib_frog/)

### solution for python(0-0)
working on ...
```
def solution(A):
    # write your code in Python 3.6
    jumps = 0
    N = len(A)
    distance = N + 1
    if N <= 2:
        return 1
    fib = fibo(N)
    print(fib)
    if distance == fib[-1]:
        return 1
    while distance > 0:
        i = -1
        while A[fib[i]] != 1:
            i = i - 1
        distance -= fib[i]
        jumps += 1
        print(distance, jumps, fib[i])
    return jumps            
    pass

def fibo(N):
    # will return fibonacci serries less than N
    fib = [0, 1]
    next_fib = 1
    while next_fib <= N:
        fib.append(next_fib)
        next_fib = fib[-1] + fib[-2]
    return fib
    
```
