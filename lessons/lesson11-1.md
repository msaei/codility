## Lesson 11: Sieve of Eratosthenes
## CountSemiprimes
link to question:(https://app.codility.com/programmers/lessons/11-sieve_of_eratosthenes/count_semiprimes/)

```
def solution(N, P, Q):
    # write your code in Python 3.6
    # get primes between 2 and second rute of N which is O(N^1/2loglogN^1/2))
    # get semiprimes between 2 and N which is O(number of primes ^ 2)
    # get create acculumutive sum for numbers between 1, N O(N)
    # iterate through P and Q and calculate the result using sum array O(N)
    pass
    
    def get_primes(N):
    primes = []
    nums = [True] * (N + 1)
    nums[0] = nums[1] = False
    i = 2
    while (i * i <= N):
        if (nums[i]):
            k = i * i
            while (k <= N):
                nums[k] = False
                k = k + i
        i = i + 1
    for i in range(2, N+1):
        if nums[i]:
            primes.append(i)
    return primes        
    pass

def get_semiprimes(N):
    semis = []
    primes = get_primes(N//2)
    print(primes)
    for i in range(0, len(primes)):
        for j in range(i, len(primes)):
            m = primes[i] * primes[j]
            if (m <= N):
                semis.append(m)
    return semis
    pass
    
def get_precount(N):
    precount = [0] * (N + 1)
    semis = get_semiprimes(N)
    for i in range(4, len(precount)):
        precount[i] = precount[i-1]
        if i in semis:
            precount[i] += 1
    return precount
        
    pass
    
```

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
