## Lesson 8: Leader
## EquiLeader
link to question: (https://app.codility.com/programmers/lessons/8-leader/equi_leader/)
### solution for python(100-100)
```
def getCountOf(B, leader):
    count = 0
    for el in B:
        if el == leader:
            count += 1
    return count
        
def solution(A):
    # write your code in Python 3.6
    N = len(A)
    B = A[:]
    B.sort()
    leader = B[int(N/2)]
    M = getCountOf(B, leader)
    firstLen = 0
    secLen = N
    leaderCount = 0
    result = 0
    for num in A:
        firstLen += 1
        secLen -= 1
        if secLen == 0:
            break
        if num == leader:
            leaderCount += 1
        if (leaderCount/firstLen>0.5) and ((M - leaderCount)/secLen)>0.5:
            result += 1

    return result
    pass
```
###solution for javascript(100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    N = A.length;
    B = A.slice(0,N);
    B.sort((a, b) => (a-b));
    let leader = B[Math.floor(N/2)];
    let M = getCountOf(B, leader);
    let flen = 0;
    let slen = N;
    let lcount = 0;
    let result = 0;
    for( i = 0; i < N-1; i++){
        flen++;
        slen--;
        if(A[i] == leader){
            lcount++;
        }
        if((lcount/flen > 0.5)&&((M-lcount)/slen>0.5)) {
            result++;
        }
    }
    return result;
}

function getCountOf(B, leader){
    let count = 0;
    for(i = 0; i < B.length; i++){
        if (B[i] == leader) {
            count++;
        }
    }
    return count;
}

```
