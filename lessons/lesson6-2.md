## Lesson 6: Sorting
## Distinct
link to question: (https://app.codility.com/programmers/lessons/6-sorting/distinct/)

## solution for javascript (100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a,b)=>(a-b));
    result = 1;
    for( i = 1; i < A.length; i++ ) {
        if (A[i] > A[i-1]){
            result++;
        }
    }
    return result;
}

```
