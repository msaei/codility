## Lesson 7: Stacks and Queues
## Nesting

link to problem: (https://app.codility.com/programmers/lessons/7-stacks_and_queues/nesting/)

### solution for python(100-100)
```
def solution(S):
    # write your code in Python 3.6
    stack = 0
    for i in range(len(S)):
        if (S[i] == '('):
            stack += 1
        else:
            stack -= 1
        if stack < 0:
            return 0
    if stack > 0:
        return 0
    return 1
    pass
    
```

### solution for javascript(100-100)
```

function solution(S) {
    // write your code in JavaScript (Node.js 8.9.4)
    stack = 0;
    for (i = 0; i < S.length; i++){
        if (S[i] == '('){
            stack++;
        }
        if (S[i] == ')'){
            stack--;
            if (stack < 0){
                return 0;
            }
        }
    }
    if (stack > 0){
        return 0;
    }
    return 1;
    
}

```
