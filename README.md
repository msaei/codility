## codility
# my solutions for codility lessons
https://app.codility.com/programmers/lessons/1-iterations/binary_gap/

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
