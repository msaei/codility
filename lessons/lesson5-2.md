## Lesson 5-2: Prefix Sums
## Passing Cars
link to question: (https://app.codility.com/programmers/lessons/5-prefix_sums/passing_cars/)

### solution in javascript (100-100)
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let passing = 0;
    eastCars = 0;
    for ( i = 0; i < A.length; i++) {
        if ( A [i] == 1) {
            passing += eastCars;
        } else {
            eastCars++;
        }
        if (passing > 1000000000) return -1;
    }
    return passing;
}

```

### solution in Java (100-100)
```
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        int passing = 0;
        int eastCars = 0;
        for (int i = 0; i < A.length; i++) {
            if ( A[i] == 1) {
                passing += eastCars;
            }else{
                eastCars++;
            }
            if(passing > 1000000000) {
                return -1;
            }
        }
        return passing;
    }
}

```

### solution for python (100-100)
```
def solution(A):
    # write your code in Python 3.6
    passing = 0
    eastCars = 0
    for i in range(len(A)):
        if (A[i] == 1):
            passing += eastCars
        else :
            eastCars += 1
        if (passing > 1000000000):
            return -1
    
    return passing
    pass
    
```
