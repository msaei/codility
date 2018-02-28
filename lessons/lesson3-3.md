## Lesson 3: Time Complexity
## PermMissingElm
link to question: (https://app.codility.com/programmers/lessons/3-time_complexity/perm_missing_elem/)

### solution for javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    N = A.length + 1;
    missed = N * (N + 1) / 2;
    for ( i = 0; i < A.length; i++) {
        missed -= A[i];
    }
    return missed;
}

```

### solution for Java
```
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        int missed = A.length + 1;
        for (int i = 0; i < A.length; i++){
            missed += i + 1 - A[i];
        }
        return missed;
    }
}

```

### solution for python
```
def solution(A):
    # write your code in Python 3.6
    missed = len(A) + 1
    for i in range (len(A)):
        missed += i + 1 - A[i]
    return missed
    pass
    
```
