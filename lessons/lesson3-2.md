## Lesson 3: Time Complexity
## frog jump
[link to question] (https://app.codility.com/programmers/lessons/3-time_complexity/frog_jmp/)

### solution in javascript
```
function solution(X, Y, D) {
    // write your code in JavaScript (Node.js 8.9.4)
    jumps = Math.floor((Y - X) / D)
    if ((Y - X) % D != 0 ) {
        jumps++;
    } 
    return jumps;
}

```

### solution in Java
```
class Solution {
    public int solution(int X, int Y, int D) {
        // write your code in Java SE 8
        int jumps = (Y - X) / D;
        if ((Y - X) % D != 0 ) {
            jumps++;
        }
        return jumps;
    }
}

```

### solution in python
```
def solution(X, Y, D):
    # write your code in Python 3.6
    jumps = (Y - X) // D
    if ((Y - X) % D != 0):
        jumps = jumps + 1
    return jumps
    pass
    
```
