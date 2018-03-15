## Lesson5-4: Prefix Sums
## MinAvgTwoSlices
link to question: (https://app.codility.com/programmers/lessons/5-prefix_sums/min_avg_two_slice/)

### solution for javascript(100-100)
logic is same as python but for resolving javascript floating point problem, 
instead of dividing by two or three I keep the sum of the numbers and times them 
by 2 or 3 to make a 6 time average and them keep it as minimum . it works ;)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let min = (A[0] + A[1]) * 3;
    let result = 0;
    for ( i = 1; i < A.length - 2; i++) {
        if ( (A[i] + A[i+1]) * 3 < min){
            min = (A[i] + A[i+1]) * 3;
            result = i;
        }
        if ( (A[i] + A[i+1] + A[i+2]) * 2 < min) {
            min = (A[i] + A[i+1] + A[i+2]) * 2;
            result = i;
        }
    }
    
    if ((A[A.length - 1] + A[A.length -2]) * 3 < min) {
        return A.length - 2;
    }
    return result;
}

```

### solution for python (100-100)
I found this in (https://codesays.com/2014/solution-to-min-avg-two-slice-by-codility/#comment-920)
```
def solution(A):
    min_avg_value = (A[0] + A[1])/2.0   # The mininal average
    min_avg_pos = 0     # The begin position of the first
                        # slice with mininal average
 
    for index in range(0, len(A)-2):
        # Try the next 2-element slice
        if (A[index] + A[index+1]) / 2.0 < min_avg_value:
            min_avg_value = (A[index] + A[index+1]) / 2.0
            min_avg_pos = index
        # Try the next 3-element slice
        if (A[index] + A[index+1] + A[index+2]) / 3.0 < min_avg_value:
            min_avg_value = (A[index] + A[index+1] + A[index+2]) / 3.0
            min_avg_pos = index
 
    # Try the last 2-element slice
    if (A[-1]+A[-2])/2.0 < min_avg_value:
        min_avg_value = (A[-1]+A[-2])/2.0
        min_avg_pos = len(A)-2
 
    return min_avg_pos
    pass
```
