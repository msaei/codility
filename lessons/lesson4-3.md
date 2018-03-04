## Lesson 4-3: Counting Elements 
## MissingInteger
link to the question: (https://app.codility.com/programmers/lessons/4-counting_elements/missing_integer/)
### solution for javascript (100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let checkList = Array(A.length).fill(0);
    for ( i = 0 ; i < A.length; i++) {
        if ( A[i] > 0 && A[i] <= A.length ) {
            checkList[A[i]-1] = 1;
        }
    }
    if ( checkList.indexOf(0) == -1 ) {
        return A.length + 1;
    } else {
        return checkList.indexOf(0) + 1;
    }

}

```
### solution for javascript (100-25) 
(works correctly but in big arrays has performance problem)
```
function solution(A) {
    for ( i = 0; i < A.length; i++) {
        if ( A.indexOf(i+1) == -1 ) {
            return (i + 1);
        }
    }
    return A.length + 1;

}

```
