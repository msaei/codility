## Lesson 3: Time Complexity
## frog jump
[link to question] (https://app.codility.com/programmers/lessons/3-time_complexity/frog_jmp/)

### solution in javascript
```
function solution(X, Y, D) {
    // write your code in JavaScript (Node.js 8.9.4)
    jumps = Math.floor((Y - X) / D)
    if ((Y - X) % D == 0 ) {
        return jumps;
    } else {
        return jumps + 1;
    }
   
}

```
