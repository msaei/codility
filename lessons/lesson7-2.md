## Lesson 7: Stacks and Queues
## Brackets

link to problem: (https://app.codility.com/programmers/lessons/7-stacks_and_queues/brackets/)

### solution in python(100-100)
```
def solution(S):
    # write your code in Python 3.6
    stack = []
    for i in range(len(S)):
        char = S[i]
        if (char in '([{'):
            stack.append(char)
            continue
        if (char in ')}]' and len(stack) == 0):
            return 0;
        if (char == ')' and stack[-1] == '('):
            stack.pop(-1)
            continue
        if (char == ']' and stack[-1] == '['):
            stack.pop(-1)
            continue
        if (char == '}' and stack[-1] == '{'):
            stack.pop(-1)
            continue
        return 0
    if (len(stack) == 0):
        return 1
    return 0
            
    pass
    
```

solution for javascript(100-100)
```
function solution(S) {
    // write your code in JavaScript (Node.js 8.9.4)
    let stack = [];
    for (i = 0; i < S.length; i++){
        if ('({['.includes(S[i])){
            stack.push(S[i]);
            continue;
        }
        if ( S[i] == ']' && stack[stack.length -1] == '['){
            stack.pop();
            continue
        }
        if ( S[i] == ')' && stack[stack.length -1] == '('){
            stack.pop();
            continue
        }
        if ( S[i] == '}' && stack[stack.length -1] == '{'){
            stack.pop();
            continue
        }
        return 0;
    }
    if (stack.length > 0){
        return 0;
    }
    
    return 1;
}

```
