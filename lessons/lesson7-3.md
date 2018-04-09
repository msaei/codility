## Lesson 7: Stacks and Queues
## Fish

link to problem: (https://app.codility.com/programmers/lessons/7-stacks_and_queues/fish/)

### solution for python(100-100)
```
def solution(A, B):
    # write your code in Python 3.6
    downStack = []
    survive = 0
    for i in range(len(A)):
        if B[i] == 0: #flowing upstream
            while len(downStack) > 0:
                if downStack[-1] > A[i]:
                    survive -= 1
                    break
                else:
                    downStack.pop(-1)
            survive += 1
        else: #flowing downstream
            downStack.append(A[i])
    survive += len(downStack)
    return survive
        
    pass
    
```

### solution for javascript(100-100)
```
function solution(A, B) {
    // write your code in JavaScript (Node.js 8.9.4)
    let downStack = [];
    let survive = 0;
    for (i = 0; i < A.length; i++){
        
        if (B[i] == 0) {
            // flowing upstream
            while (downStack.length > 0) {
                if (A[i] < downStack[downStack.length - 1]){
                    //the fish got eaten
                    survive--;
                    break;
                } else {
                    //the fish ate fish
                    downStack.pop()
                }
            }
            survive++;
            
        } else {
            //flowing downstream
            downStack.push(A[i]);
        }
    }
    survive += downStack.length;
    return survive;
}

```
