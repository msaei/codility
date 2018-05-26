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

### solution for python(100-100)
got from codesays weblog (https://codesays.com/2014/solution-to-fib-frog-by-codility/)
```
def get_jumps(N):
    f = [1, 1]
    while f[-1] < N:
        f.append(f[-1] + f[-2])
    return f[1:-1]  # strip fisrt and last element
 
def solution(A):
    # add frog's starting position to A
    A.insert(0, 1)
    # add frog's destination position to A
    A.append(1)
 
    n = len(A)
 
    # store avaliable fibonacci jumps
    steps = get_jumps(n)
 
    # we _can_ do at most n-1 jumps, so let ‘infinity’ := n,
    oo = n
 
    # S[i] <-- minimal jumps count to get to the position i
    S = [oo] * n
    S[0] = 0
    # dynamic programming...
    for position in range(1, len(S)):
        s_min = oo
        for jump in steps:
            prev_leaf = position - jump
            if prev_leaf >= 0:
                if A[prev_leaf] == 1 and S[prev_leaf] + 1 < s_min:
                    s_min = S[prev_leaf] + 1
            else:
                break
        S[position] = s_min
 
    return S[-1] if S[-1] != oo else -1
    pass
    
```
