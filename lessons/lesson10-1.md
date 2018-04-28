## Lesson 10: Prime and composite numbers
## CountFactors
link to question: (https://app.codility.com/programmers/lessons/10-prime_and_composite_numbers/count_factors/)

### solution for python(100-100)
```
def solution(N):
    # write your code in Python 3.6
    i = 1
    result = 0
    while i * i < N:
        if N % i == 0:
            result += 2
        i += 1
    if i * i == N:
        result += 1
    return result
    pass
    
```
