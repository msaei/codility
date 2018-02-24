## Lesson 2: Arrays
## OddOccurrencesInArray 
[link to the question] (https://app.codility.com/programmers/lessons/2-arrays/odd_occurrences_in_array/)
### solution in javascript
```
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let result = 0;
    for ( i = 0; i < A.length; i++) {
        result = result ^ A[i];
    }
    return result;
}

```
### solution in Java
```
class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 8
        int result = 0;
        for ( int i = 0; i < A.length; i++) {
            result = result ^ A[i];
        }
        return result;
    }
}

```
