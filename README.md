# codility
## my solutions for codility lessons

 Lesson 1: [BinaryGap] (https://app.codility.com/programmers/lessons/1-iterations/binary_gap/)
### solution in javascript
```
  function solution(N) {
    
    let max_gap = 0;
    let started = false;
    let gap = 0;
    let remain = 0;
    
    
    while ( N > 1) {
        remain = N % 2;
        
        if (remain == 1) {
            started = true;
            if (gap > max_gap) { max_gap = gap };
            gap = 0;
        } else if ( started == true) {
            gap++;
        }
        
        N = Math.round( (N - remain) / 2);
    }
    if ( gap > max_gap ) { max_gap = gap };
    return max_gap;
  }
```

### solution in Java
```
class Solution {
    public int solution(int N) {
        // write your code in Java SE 8
        int gap = 0;
        int maxGap = 0;
        int remain = 0;
        boolean started = false;
        
        while (N > 0){
            remain = N % 2;
            if (remain == 1) {
                started = true;
                if ( gap > maxGap ) { maxGap = gap; }
                gap = 0;
            } else if ( started == true ) {
                gap++;
            }
            N = N / 2;
        }
        if ( gap > maxGap ) { maxGap = gap; }
        return maxGap;
    }
}
```
