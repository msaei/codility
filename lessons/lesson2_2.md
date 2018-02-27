## Lesson 2: Arrays
## CyclicRotation
[link to the question] (https://app.codility.com/programmers/lessons/2-arrays/cyclic_rotation/)
### solution in javascript

```
function solution(A, K) {
    // write your code in JavaScript (Node.js 8.9.4)
    let item = 0;
    K = K % A.length;
    for ( i = 0; i < K; i++) {
        item = A.pop();
        A.unshift(item);
    }
    return A;
}

```
### solution in javascript (second solution)

```
function solution(A, K) {
    // write your code in JavaScript (Node.js 8.9.4)
    K = K % A.length;
    let startIndex = A.length - K;
    let removed = A.splice(startIndex, K);
    removed.reverse();
    removed.map(x => A.unshift(x));
    return A;
}

```

### solution in Java

```
class Solution {
    public int[] solution(int[] A, int K) {
        // write your code in Java SE 8
        if ( A.length == 0 ) {
            return A;
        }
        int[] B = new int[A.length];
        K = K % A.length;
        for ( int i = 0; i < A.length; i++) {
            if ( i + K < A.length) {
                B[i + K] = A[i];
            } else {
                B[i + K - A.length] = A[i];
            }
        }
        return B;
    }
}

```

### solution in python

```
def solution(A, K):
    # write your code in Python 3.6
    if len(A) == 0:
        return A;
    K = K % len(A)
    for i in range(K):
        item = A.pop()
        A.insert(0, item)
    return A;
    pass
    
 ```
