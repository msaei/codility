## Lesson 4: Counting Elements
## forgRiverOne
link to question: (https://app.codility.com/programmers/lessons/4-counting_elements/frog_river_one/)
### solution for javascript (100-100)
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let route = Array(X).fill(0);
    let steps = 0;
    for ( i = 0; i < A.length; i++ ) {
        if ( route[A[i] -1] == 0 ) {
            route[A[i] - 1] = 1;
            steps++;
        }
        
        if (steps == X) {
            return i;
        }
    }
    return -1;
}

### solution for javascript 1 (100-60)
(works correctly but has performance issue for big arrays)
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let B = Array(X).fill(1);

    for ( i = 0; i < A.length; i++ ) {
        B[A[i] - 1] = 0;
        if (B.indexOf(1) == -1) {
            return i;
        }
    }
    return -1;
}

```

### solution for javascript 2 (100-60)
(works correctly but has performance issue for big arrays)
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let = lastLeave = 0;
    let = happenTime = 0;
    if (X > A.length) {
        return -1;
    }
    for ( i = 1; i <= X; i++){
        happenTime = A.indexOf(i);
        if (happenTime == -1 ){
            return -1;
        }
        if (happenTime > lastLeave){
            lastLeave = happenTime;
        }
        
    }
    return lastLeave;
}

```

### solution for javascript 3 (40-40)
(works properly for X les than 5; problem of bitwise operation which parse number to 32 bits only)
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let val = 0;
    let route = 0;
    let complete = Math.pow(2,X) - 1;
    //console.log(Math.pow(2,0));
    for ( i = 0; i < A.length; i++) {
        val = Math.pow(2,(A[i]-1));
        route = route | val ;
        console.log(route);
        if ( route == complete ) {
            return i;
        }
    }
    return i = -1;
}

```

### solution for javascript 4 (100-40)
(works corectly but has performane issue for big arrays)
```
function solution(X, A) {
    // write your code in JavaScript (Node.js 8.9.4)
    if (A.length < X) {
        return -1;
    }
    let route = [];
    
    //console.log(Math.pow(2,0));
    for ( i = 0; i < A.length; i++) {
        if ((A[i] <= X) && (route.indexOf(A[i]) == -1)) {
            route.push(A[i]);
        }
        if (route.length == X) {
            return i;
        }
        //console.log(route);
    }
    return i = -1;
}

```
