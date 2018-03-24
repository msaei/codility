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

### solution for Java()
```

import java.util.Arrays;

class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        Arrays.sort(A);
        int N = A.length;
        int max = A[N-1] * A[N-2] * A[N-3];
        int tempMax = A[0] * A[1] * A[N-1];
        if (tempMax > max)
        return tempMax;
        return max;
    }
}

```

### solution for python(100-100)
```

def solution(A):
    # write your code in Python 3.6
    A.sort()
    max = A[-1] * A[-2] * A[-3]
    tempMax = A[0] * A[1] * A[-1]
    if (tempMax > max):
        return tempMax
    return max
    pass
    
```
