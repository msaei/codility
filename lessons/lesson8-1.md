## Lesson 8: Leader
## Dominator
link to question: (https://app.codility.com/programmers/lessons/8-leader/dominator/)

### solution for python(100-100)
```
def solution(A):
    # write your code in Python 3.6
    
    if len(A) < 2:
        return len(A) - 1
    counter = 0
    
    B = A[:]
    B.sort()
    candid = B[len(B)//2]
    for i in range(len(A)):
        if A[i] == candid:
            counter = counter + 1
    if counter > len(A)//2:
        return A.index(candid)
    return -1
    
    pass
    
```

### solution for javascript(100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    N = A.length;
    if (N == 0) {
        return -1;
    }
    if (N < 3) {
        return 0;
    }
    B = A.slice();
    B.sort((a, b) => (a-b));
    let candid = B[Math.floor(N/2)];
    let count = 0;
    for (i=0; i<N; i++){
        if (B[i] == candid){
            count++;
        }
    }
    if (count > Math.floor(N/2)) {
        return A.indexOf(candid);
    }
    return -1;
}

```
