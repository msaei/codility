## Sieve of Eratosthenes
## CountNonDivisible
link to question: (https://app.codility.com/programmers/lessons/11-sieve_of_eratosthenes/count_non_divisible/)

### solution for python(100-100)
performance detail:(https://app.codility.com/demo/results/trainingA65QZ3-TWH/)
got part of solution from:(https://codesays.com/2014/solution-to-count-non-divisible-by-codility/)
```
def solution(A):
    # write your code in Python 3.6
    numbers_count = get_numbers_count(A)
    divisors_dic = get_divisors(A)
    N = len(A)
    result = []
    for num in A:
        non_div_count = N
        divisors = divisors_dic[num]
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


def get_divisors(A):
    from math import sqrt
    A_max = max(A)
    # Compute the divisors for each element in A
    divisors = {}
    for element in A:
        # Every nature number has a divisor 1.
        divisors[element] = [1]
    # In this for loop, we only find out all the
    # divisors less than sqrt(A_max), with brute
    # force method.
    for divisor in range(2, int(sqrt(A_max))+1):
        multiple = divisor
        while multiple  <= A_max:
            if multiple in divisors and not divisor in divisors[multiple]:
                divisors[multiple].append(divisor)
            multiple += divisor
    # In this loop, we compute all the divisors
    # greater than sqrt(A_max), filter out some
    # duplicate ones, and combine them.
    for element in divisors:
        temp = [int(element/div) for div in divisors[element]]
        # Filter out the duplicate divisors
        temp = [item for item in temp if item not in divisors[element]]
        divisors[element].extend(temp)
    return divisors
    pass

```
