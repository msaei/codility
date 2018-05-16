## Sieve of Eratosthenes
## CountNonDivisible
link to question: (https://app.codility.com/programmers/lessons/11-sieve_of_eratosthenes/count_non_divisible/)

### solution for python(100-50-77)
performance problem
link:(https://app.codility.com/demo/results/trainingUATJZ3-A5U/)
```
def solution(A):
    # write your code in Python 3.6
    numbers_count = get_numbers_count(A)
    N = len(A)
    result = []
    for num in A:
        non_div_count = N
        divisors = get_divisors(num)
        for divisor in divisors:
            non_div_count -= numbers_count[divisor]
        result.append(non_div_count)
    return result
    pass

def get_numbers_count(A):
    N = len(A)
    numbers = [0] * (2 * N + 1)
    for i in range(N):
        numbers[A[i]] += 1
    return numbers
    pass

def get_divisors(x):
    divisors = []
    i = 1
    while i * i <= x:
        if x % i == 0:
            divisors.append(i)
            if i != x//i:
                divisors.append(x//i)
        i += 1
    return divisors
    pass

```
