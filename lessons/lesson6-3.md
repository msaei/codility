## Lesson 6: Sorting
## MaxProductOfThree
link to question: (https://app.codility.com/programmers/lessons/6-sorting/max_product_of_three/)

### solution for javascript(100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a, b)=>(a-b));
    const n = A.length;
    let max = A[n-1] * A[n-2] * A[n-3];
    // check for specific cases
    let spMax = A[0] * A[1] * A[n-1];
    if (spMax > max) { max = spMax; }
    
    return max;
}

```
