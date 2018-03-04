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
