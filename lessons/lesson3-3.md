## Lesson 3: Time Complexity
## PermMissingElm
link to question: (https://app.codility.com/programmers/lessons/3-time_complexity/perm_missing_elem/)

### solution for javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    N = A.length + 1;
    missed = N * (N + 1) / 2;
    for ( i = 0; i < A.length; i++) {
        missed -= A[i];
    }
    return missed;
}

```
