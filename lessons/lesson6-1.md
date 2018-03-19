## Lesson 6: Sorting
## Triangle
link to question (https://app.codility.com/programmers/lessons/6-sorting/triangle/)

### solution for javascript (0-0)
works on test set
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a,b)=>(a-b));
    let bigLeg = 0;
    let midLeg = 0;
    let smlLeg = 0;
    let result = 0;
    let index = 0;
    
    while (A.length > 2) {
        bigLeg = A.pop();
        midLeg = A[A.length - 1];
        index = A.length - 2;
        while ( (index >= 0) && ((A[index] + midLeg) > bigLeg) ){
            //console.log(bigLeg,", ", midLeg, ", ", A[index] );
            result ++;
            index--;
        }
    }
    return result;
     
}

```

### refactor javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a,b)=>(a-b));
    let b = [];
    if ( A.length == 0 ) {
        return 0;
    }
    b.push(A[0]);
    for (i = 1 ; i < A.length; i++ ){
        if (A[i] != A[i-1]) {
            b.push(A[i]);
        }
    }
    let bigLeg = 0;
    let midLeg = 0;
    let smlLeg = 0;
    let result = 0;
    let index = 0;
    
    while (b.length > 2) {
        bigLeg = b.pop();
        midLeg = b[b.length - 1];
        index = b.length - 2;
        while ( (index >= 0) && ((A[index] + midLeg) > bigLeg) ){
            //console.log(bigLeg,", ", midLeg, ", ", A[index] );
            result ++;
            index--;
        }
    }
    return result;
     
}

```
