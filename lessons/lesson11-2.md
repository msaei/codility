## Sieve of Eratosthenes
## CountNonDivisible
link to question: (https://app.codility.com/programmers/lessons/11-sieve_of_eratosthenes/count_non_divisible/)
```
def arrayF(n):
    F = [0] * (n+1)
    i = 2
    while (i * i <= n):
        if (F[i] == 0):
            k = i * i
            while (k <= n):
                if (F[k] == 0):
                    F[k] = i
                k += i
        i += 1
    return F
    pass
        
def factorization(x):
    F = arrayF(x)
    y = x
    primeFactors = []
    while (F[x] > 0):
        primeFactors += [F[x]]
        x //= F[x]
    primeFactors += [x]
    return primeFactors
    pass
    
```
