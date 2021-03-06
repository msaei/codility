## Lesson 4-4: Counting Elements 
## MaxCounters
link to the question: (https://app.codility.com/programmers/lessons/4-counting_elements/max_counters/)
### solution for javascript (100-100)
```
function solution(N, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let result = Array(N).fill(0);
    let max = 0;
    let maxCounter = 0;
    for ( i = 0; i < A.length; i++ ) {
        if ( A[i] == N + 1 ) {
           maxCounter = max; 
        } else {
            if (result[A[i] - 1] < maxCounter) {
                result[A[i] - 1] = maxCounter;
            }
            result[A[i] - 1]++;
            if (result[A[i] - 1] > max){
                max = result[A[i] - 1];
            }
            
        }
    }
    
    for (i = 0; i < result.length; i++){
        if ( result[i] < maxCounter) {
            result[i] = maxCounter;
        }
    }
    return result;
}

```

###  solution for Java (100-100)
```
import java.util.*;
class Solution {
    public int[] solution(int N, int[] A) {
        // write your code in Java SE 8
        int result[] = new int[N];
        Arrays.fill(result, 0);
        int max = 0;
        int counterMax = 0;
        
        for (int i = 0; i < A.length; i++) {
            if ( A[i] > N ) {
                counterMax = max;
            } else {
                if ( result[A[i] - 1] < counterMax) {
                    result[A[i] - 1] = counterMax;
                }
                result[A[i] - 1]++;
                if (result[A[i] - 1] > max) {
                    max = result[A[i] - 1];
                }
            }
        }
        
        for (int j = 0; j < result.length; j++) {
            if ( result[j] < counterMax) {
                result[j] = counterMax;
            }
        }
        return result;
    }
}

```
### solution for python (100-100)
```
def solution(N, A):
    # write your code in Python 3.6
    counters = [0] * N
    max = 0
    maxCounter = 0
    for i in range(len(A)):
        if (A[i] > N) :
            maxCounter = max
        else :
            if (counters[A[i] - 1] < maxCounter):
                counters[A[i] - 1] = maxCounter
            counters[A[i] - 1] += 1
            if (counters[A[i] - 1] > max):
                max = counters[A[i] - 1]
    
    for i in range(N):
        if (counters[i] < maxCounter):
            counters[i] = maxCounter
    
    return counters
    pass
    
```

### solution for javascript (100-60)
(works properly but has performance issue with large size arrays)
```
function solution(N, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let result = Array(N).fill(0);
    let max = 0;
    for ( i = 0; i < A.length; i++ ) {
        if ( A[i] == N + 1 ) {
           result.fill(max); 
        } else {
            result[A[i] - 1]++;
            if (result[A[i] - 1] > max){
                max = result[A[i] - 1];
            }
            
        }
    }
    return result;
}

```
