## Lesson 11: Sieve of Eratosthenes
## CountSemiprimes
link to question:(https://app.codility.com/programmers/lessons/11-sieve_of_eratosthenes/count_semiprimes/)


### solution in python(100 - 100)
performance problem
```

def solution(N, P, Q):
    # write your code in Python 3.6
    precount = get_precount(N)
    result = []
    for i in range(len(P)):
        result.append(precount[Q[i]] - precount[P[i] - 1])
    return result
    pass

def get_primes(N):
    nums = [-1] * (N + 1)
    nums[0] = nums[1] = 1
    i = 2
    while (i * i <= N):
        if (nums[i] == -1):
            k = i * i
            while (k <= N):
                nums[k] = i
                k = k + i
        i = i + 1
    return nums
            
    pass

def get_precount(N):
    precount = [0] * (N + 1)
    primes = get_primes(N)
    for i in range(4, len(precount)):
        precount[i] = precount[i-1]
        first_factor = primes[i]
        second_factor = i // first_factor
        if (primes[i] != -1 and primes[first_factor] == -1 and primes[second_factor] == -1):
            precount[i] += 1
    return precount
        
    pass


```
