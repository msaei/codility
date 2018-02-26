Lesson 2

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
or

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
