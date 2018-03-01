## Lesson 4: Counting Elements
## PremCheck
link to question: (https://app.codility.com/programmers/lessons/4-counting_elements/perm_check/)

### solution for javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let result = 0;
    for (i = 0; i < A.length; i++){
        result = result ^ ((i + 1) ^ A[i]);
    }
    return ((result == 0) ? 1 : 0);
}

```

### solution for Java
```
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        int result = 0;
        for (int i = 0; i < A.length; i++) {
            result = result ^ ((i + 1) ^ A[i]);
        }
        if ( result == 0 ){
            return 1;
        }
        return 0;
    }
}

```

### solution for python
```
def solution(A):
    # write your code in Python 3.6
    result = 0
    for i in range(len(A)):
        result = result ^ ((i + 1) ^ A[i])
    if (result == 0):
        return 1
    return 0
    pass
    
```
