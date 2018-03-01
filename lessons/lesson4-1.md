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
