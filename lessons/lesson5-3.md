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

### solution for Java(100-0)
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

### solution for Java (100-100)
I found it in the stackoveflow which is very cool solution
```
public static int[] solveGenomicRange(String S, int[] P, int[] Q) {
        //used jagged array to hold the prefix sums of each A, C and G genoms
        //we don't need to get prefix sums of T, you will see why.
        int[][] genoms = new int[3][S.length()+1];
        //if the char is found in the index i, then we set it to be 1 else they are 0
        //3 short values are needed for this reason
        short a, c, g;
        for (int i=0; i<S.length(); i++) {
            a = 0; c = 0; g = 0;
            if ('A' == (S.charAt(i))) {
                a=1;
            }
            if ('C' == (S.charAt(i))) {
                c=1;
            }
            if ('G' == (S.charAt(i))) {
                g=1;
            }
            //here we calculate prefix sums. To learn what's prefix sums look at here https://codility.com/media/train/3-PrefixSums.pdf
            genoms[0][i+1] = genoms[0][i] + a;
            genoms[1][i+1] = genoms[1][i] + c;
            genoms[2][i+1] = genoms[2][i] + g;
        }
        int[] result = new int[P.length];
        //here we go through the provided P[] and Q[] arrays as intervals
        for (int i=0; i<P.length; i++) {
            int fromIndex = P[i];
            //we need to add 1 to Q[i], 
            //because our genoms[0][0], genoms[1][0] and genoms[2][0]
            //have 0 values by default, look above genoms[0][i+1] = genoms[0][i] + a; 
            int toIndex = Q[i]+1;
            if (genoms[0][toIndex] - genoms[0][fromIndex] > 0) {
                result[i] = 1;
            } else if (genoms[1][toIndex] - genoms[1][fromIndex] > 0) {
                result[i] = 2;
            } else if (genoms[2][toIndex] - genoms[2][fromIndex] > 0) {
                result[i] = 3;
            } else {
                result[i] = 4;
            }
        }

        return result;
    }
    
```

### solution for python(100-100)
```
def solution(S, P, Q):
    # write your code in Python 3.6
    part = ''
    result = [0]*len(P)
    for i in range(len(P)):
        part = S[P[i]:Q[i]+1]
        result[i] = getMin(part)
    return result
    pass

def getMin(str):
    if 'A' in str:
        return 1
    if 'C' in str:
        return 2
    if 'G' in str:
        return 3
    if 'T' in str:
        return 4
```
