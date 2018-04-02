## Lesson 7: Stacks and Queues
## StoneWall

link to problem: (https://app.codility.com/programmers/lessons/7-stacks_and_queues/stone_wall/)

### solution for python(100-100)
```
def solution(H):
    # write your code in Python 3.6
    stones = []
    N = 0
    stones.append(H[0])
    lastStone = H[0]
    
    for i in range(1, len(H)):

        if (H[i] == lastStone):
            continue
        
        while (H[i] < lastStone):
            N += 1
            stones.pop(-1)
            if (len(stones) == 0):
                lastStone = 0
            else:
                lastStone = stones[-1]
                
        if (H[i] > lastStone):
            stones.append(H[i])
            lastStone = H[i]
            continue
    
    N += len(stones)
    return N
    
```

### solution for javascript
```
function solution(H) {
    // write your code in JavaScript (Node.js 8.9.4)
    let blocks = 0;
    const N = H.length;
    let stones = [];
    stones.push(H[0]);
    let lastStone = H[0];
    
    for (i = 1; i < N; i++){
        
        if (H[i] == lastStone){
            continue;
        }

        while (H[i] < lastStone){
            stones.pop();
            blocks++;
            if ( stones.length == 0){
               lastStone = 0;
            } else {
               lastStone = stones[stones.length -1];
            }
        }
        if (H[i] > lastStone){
            stones.push(H[i]);
            lastStone = H[i];
        }

    }
    
    blocks += stones.length;
    return blocks;
    
}

```
