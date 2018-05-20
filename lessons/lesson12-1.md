## Lesson 12: Euclidean algorithm
## ChocolatesByNumbers
link to question: (https://app.codility.com/programmers/lessons/12-euclidean_algorithm/chocolates_by_numbers/)  

the answer is lcm(N, M) divided by M, and since lcm(N, M) = N * M / gcd(N, M) divide by M, the answer is N / gcd(N, M)
### solution for python(100-50)
link to performance detail: (https://app.codility.com/demo/results/trainingNG6KFN-4Q5/)
```
def solution(N, M):
    # write your code in Python 3.6
    # find lcd(N, M) and divide by M and it is equal to N divide by gcd(N, M)
    g = gcd(N, M)
    return N // g
    pass

def gcd(N, M):
    if N == M :
        return N
    if N > M :
        return gcd(N-M, M)
    else:
        return gcd(N, M-N)

```
