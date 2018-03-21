## Lesson 6: Sorting
## Triangle
link to question (https://app.codility.com/programmers/lessons/6-sorting/triangle/)

### solution for javascript (100-100)
works on test set
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a,b)=>(a-b));
    if ( A.length < 3) {
        return 0;
    }
    for ( i = 0; i < A.length -2; i++) {
        if ( A[i] + A[i + 1] > A[i+2]) {
            return 1;
        }
    }
    return 0;
}

```

### solution for Java(100-100)
for resolve the overflow problem used BigInteger
```
import java.util.Arrays;
import java.math.BigInteger;
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        Arrays.sort(A);
        if ( A.length < 3 ) 
        return 0;
        
        for (int i = 0; i < A.length -2; i++){
            
            if ( BigInteger.valueOf(A[i]).add(BigInteger.valueOf(A[i+1])).compareTo(BigInteger.valueOf(A[i+2])) > 0) {
                return 1;
            }
        }
        return 0;
    }
}
```
