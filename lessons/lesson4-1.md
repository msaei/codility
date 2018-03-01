## Lesson 4: Counting Elements
## PremCheck
link to question: (https://app.codility.com/programmers/lessons/4-counting_elements/perm_check/)

### solution for javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let result = 0;
    for (i = 0; i < A.length; i++){
        result = result ^ ((i + 1) ^ A[i]);
    }
    return ((result == 0) ? 1 : 0);
}

```
