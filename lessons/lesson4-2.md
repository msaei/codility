## Lesson 4: Counting Elements
## forgRiverOne
link to question: (https://app.codility.com/programmers/lessons/4-counting_elements/frog_river_one/)

### solution for javascript
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let B = Array(X).fill(1);

    for ( i = 0; i < A.length; i++ ) {
        B[A[i] - 1] = 0;
        if (B.indexOf(1) == -1) {
            return i;
        }
    }
    return -1;
}

```
