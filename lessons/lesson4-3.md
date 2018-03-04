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

### solution for java (100-100)
```
import java.util.*;
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        int list[] = new int[A.length];
        Arrays.fill(list, 0);
        for (int i = 0; i < A.length; i++) {
            if (A[i] > 0 && A[i] <= A.length) {
                list[A[i] -1] = 1;
            }
        }
        
        for (int i = 0; i < list.length; i++ ){
            if ( list[i] == 0) {
                return i + 1;
            }
        }
        return A.length + 1;

    }
}

```

### solution for python (100-100)
```
def solution(A):
    # write your code in Python 3.6
    checkList = [0] * len(A);
    for i in range ( len(A) ):
        if ( A[i] > 0 and A[i] <= len(A) ):
            checkList[A[i] - 1] = 1;
    try:
        missed = checkList.index(0)
    except:
        return len(A)+1;
    return missed + 1;
    pass
    
```
### solution for java (100-100) 
(cool solution I found in the stack overflow)
```
public int solution(int[] A) {
        // write your code in Java SE 8
        Arrays.sort(A);
        int y = 1;
        for (int i = 0; i < A.length; i++) {
            if (y < A[i]) {
                return y;
            }
            if (y == A[i])
                y++;
        }
        return y;
    }

```
