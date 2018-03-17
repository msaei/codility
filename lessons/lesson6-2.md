## Lesson 6: Sorting
## Distinct
link to question: (https://app.codility.com/programmers/lessons/6-sorting/distinct/)

### solution for javascript (100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    A.sort((a,b)=>(a-b));
    result = 1;
    for( i = 1; i < A.length; i++ ) {
        if (A[i] > A[i-1]){
            result++;
        }
    }
    return result;
}

```

### solution for Java (100-100)
```
import java.util.Arrays;
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        if ( A.length == 0 )
        return 0;
        int result = 1;
        Arrays.sort(A);
        for ( int i = 1; i < A.length; i++) {
            if (A[i] > A[i-1])
            result++;
        }
        return result;
    }
}

```

### solution for python(100-100)
```
def solution(A):
    # write your code in Python 3.6
    if len(A) == 0:
        return 0
    result = 1
    A.sort()
    for i in range(1, len(A)):
        if A[i] != A[i-1]:
            result += 1
    return result
    pass
    
```
