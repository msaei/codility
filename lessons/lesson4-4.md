## Lesson 4-4: Counting Elements 
## MaxCounters
link to the question: (https://app.codility.com/programmers/lessons/4-counting_elements/max_counters/)
### solution for javascript (100-100)


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
