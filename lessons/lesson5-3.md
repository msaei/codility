## Lesson5-3: Prefix Sums
## GenomicRangeQuery
link to question: (https://app.codility.com/programmers/lessons/5-prefix_sums/genomic_range_query/)

### solution for javascript(100-100)
```
function solution(S, P, Q) {
    // write your code in JavaScript (Node.js 8.9.4)
    part = '';
    result = Array(P.length).fill(0);
    for (i = 0; i < P.length; i++) {
        part = S.substring(P[i], Q[i] +1);
        result[i] = getmin(part);
    }
    return result;
}

function getmin (str) {
    if (str.includes('A')) return 1;
    if (str.includes('C')) return 2;
    if (str.includes('G')) return 3;
    if (str.includes('T')) return 4;
}

```

### solution for Java
```
import java.util.*;
class Solution {
    public int[] solution(String S, int[] P, int[] Q) {
        // write your code in Java SE 8
        String part ;
        int result[] = new int[P.length];
        Arrays.fill(result, 0);
        for ( int i = 0; i < P.length; i++) {
            part = S.substring(P[i], Q[i] + 1);
            result[i] = getmin(part);
        }
        return result;
    }
    
    private int getmin(String str) {
        if (str.indexOf('A') >= 0) return 1;
        if (str.indexOf('C') >= 0) return 2;
        if (str.indexOf('G') >= 0) return 3;
        if (str.indexOf('T') >= 0) return 4;
        return -1;
    }
}

```
