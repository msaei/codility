## Lesson 10: Prime and composite numbers
## MinPerimeterRectangle

link to question: (https://app.codility.com/programmers/lessons/10-prime_and_composite_numbers/min_perimeter_rectangle/)

### solution for python(100-100)
```
def solution(N):
    # write your code in Python 3.6
    i = 1
    while i * i <= N :
        if N % i == 0:
            result = 2 * i + 2 * N / i
        i += 1
    return int(result)
        
    pass
    
```
