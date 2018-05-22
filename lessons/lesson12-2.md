## Lesson 12: Euclidean algorithm
## CommonPrimeDivisors
link to question: (https://app.codility.com/programmers/lessons/12-euclidean_algorithm/common_prime_divisors/)

### solution for python(100-100):

smart and clean solution from Code Says (https://codesays.com/2014/solution-to-common-prime-divisors-by-codility/)  
performance detail: (https://app.codility.com/demo/results/trainingMT59FW-742/)
```
def gcd(x, y):
    ''' Compute the greatest common divisor.
    '''
    if x%y == 0:
        return y;
    else:
        return gcd(y, x%y)
 
def removeCommonPrimeDivisors(x, y):
    ''' Remove all prime divisors of x, which also exist in y. And
        return the remaining part of x.
    '''
    while x != 1:
        gcd_value = gcd(x, y)
        if gcd_value == 1:
            # x does not contain any more
            # common prime divisors
            break
        x /= gcd_value
    return x
 
def hasSamePrimeDivisors(x, y):
    gcd_value = gcd(x, y)   # The gcd contains all
                            # the common prime divisors
 
    x = removeCommonPrimeDivisors(x, gcd_value)
    if x != 1:
        # If x and y have exactly the same common
        # prime divisors, x must be composed by
        # the prime divisors in gcd_value. So
        # after previous loop, x must be one.
        return False
 
    y = removeCommonPrimeDivisors(y, gcd_value)
 
    return y == 1
 
def solution(A, B):
    count = 0
    for x,y in zip(A,B):
        if hasSamePrimeDivisors(x,y):
            count += 1
    return count
    
```
