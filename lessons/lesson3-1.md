
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    const reducer = (accumulator, currentValue) => accumulator + currentValue;
    total = A.reduce(reducer);
    
    diff = 2 * A[0] - total;
    if(diff == 0) {
            return 0;
        }
    minDiff = Math.abs(diff);
    
    for ( i = 1; i < (A.length - 1); i++) {
        diff = diff + 2 * A[i];
        if(diff == 0) {
            return 0;
        }
        if (Math.abs(diff) < minDiff) {
            minDiff = Math.abs(diff);
        }
    }
    return minDiff
}

```
