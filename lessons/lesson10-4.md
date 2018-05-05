## Lesson 10: Prime and composite numbers
## Peaks
link to question: (https://app.codility.com/programmers/lessons/10-prime_and_composite_numbers/peaks/start/)

###solution for python(100-100):
```
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    if N < 3:
        return 0
    peaks = get_peaks(A)
    factors = get_factors(N)
    for factor in factors:
        if factor > 2:
            check = True
            for i in range(0, N, factor):
                if peaks.find('p',i, i+factor) == -1:
                    check = False
            if check:
                return int(N/factor)
    return 0
    pass


def get_factors(N):
    i = 1
    factors = []
    factor_products = []
    while i * i < N:
        if N % i == 0:
            factors.append(i)
            factor_products = [int(N / i)] + factor_products
        i = i + 1
    if i * i == N:
        factors.append(i)
    return factors + factor_products
    pass
        
def get_peaks(A):
    # write your code in Python 3.6
    N = len(A)
    peaks = 'n'
    leftHeight = A[0]
    middleHeight = A[1]
    for i in range(2, N):
        rightHeight = A[i]
        if middleHeight > leftHeight and middleHeight > rightHeight:
            peaks += 'p'
        else:
            peaks += 'n'
        leftHeight, middleHeight = middleHeight, rightHeight
    
    return peaks
    pass

```
    
