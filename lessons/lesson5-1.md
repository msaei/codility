## Lesson 5-1 : Prefix Sums
## CountDiv
link to question (https://app.codility.com/programmers/lessons/5-prefix_sums/count_div/)

### solution for javascript (100-100)
```
function solution(A, B, K) {
    // write your code in JavaScript (Node.js 8.9.4)
   let result = Math.floor( B / K ) - Math.floor( A / K );
   if ( (A % K) == 0 ){
       result++;
   }
   
   return result;
}

```

### solution for Java (100-100)
```
class Solution {
    public int solution(int A, int B, int K) {
        // write your code in Java SE 8
        int result = (B / K);
        result -= (A / K);
        if ( A % K == 0)
        result++;
        return result;
    }
}

```
