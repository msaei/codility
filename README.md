## codility
# my solutions for codility lessons
https://app.codility.com/programmers/lessons/1-iterations/binary_gap/

```
  function solution(N) {
    
    let gap = 0;
    let started = false;
    let count = 0;
    let remain = 0;
    
    
    while ( N > 1) {
        remain = N % 2;
        
        if (remain == 1) {
            started = true;
            if (count > gap) { gap = count };
            count = 0;
        } else if ( started == true) {
            count++;
        }
        
        N = Math.round( (N - remain) / 2);
    }
    if ( count > gap ) { gap = count };
    return gap;
  }
```
