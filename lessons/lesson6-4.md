## Lesson 6: Sorting
## NumberOfDiscIntersections
link to question: (https://app.codility.com/programmers/lessons/6-sorting/number_of_disc_intersections/)

### solution for python(100-100)
```
def solution(A):
    # write your code in Python 3.6
    if (len(A) < 2):
        return 0
    rightEdges = [0] * len(A)
    leftEdges = [0] * len(A)
    for i in range(len(A)):
        rightEdges[i] = i + A[i]
        leftEdges[i] = i - A[i]
    rightEdges.sort()
    leftEdges.sort()
    
    intersections = 0
    leyers = 0
    while (len(rightEdges) > 0):
        rightEdge = rightEdges.pop(-1)
        while (rightEdge < leftEdges[-1]):
            leftEdges.pop(-1)
            leyers -= 1
        intersections += leyers
        if (intersections > 10000000):
            return -1
        leyers += 1
        leftEdge = leftEdges[-1]
        
    return intersections
    pass
    
```

### solution for python
```
def solution(A):
    B = [0] * len(A)
    C = [0] * len(A)
    overDisk = 0
    intersections =0
    
    if (len(A) < 2):
        return 0
    # calculate for first disk
    rightBound = A[0]
    if (rightBound >= len(A)):
        rightBound = len(A) - 1
    B[rightBound] += 1
    if (rightBound > 0):
            overDisk += 1
    
        
    for i in range(1, len(A)):
        
        # calculate prefix sum of left intersections
        C[i] = C[i-1] + B[i]
        overDisk -= B[i]
        # calculate left bound
        leftBound = i - A[i]
        if (leftBound < 0):
            leftBound = 0
        # add left side intersections
        intersections += C[i] - C[leftBound -1]
        intersections += overDisk
        # calculate right bound
        rightBound = i + A[i]
        if (rightBound >= len(A)):
            rightBound = len(A) - 1
        # move affect of disk to right boundry
        B[rightBound] += 1
        # calculate over passed disk boundry
        if (rightBound > i):
            overDisk += 1
        
        
        
    return intersections
        
        
    # write your code in Python 3.6
    pass
    
```
### solution for Java
I found it in this blog (https://rafal.io/posts/codility-intersecting-discs.html)
```
public static int intersectingDiscs(int[] A){
    int l = A.length;

    long[] A1 = new long[l];
    long[] A2 = new long[l];
    
    for(int i = 0; i < l; i++){
      A1[i] = (long)A[i] + i;
      A2[i] = -((long)A[i]-i);
    }
    
    Arrays.sort(A1);
    Arrays.sort(A2);
    
    long cnt = 0;
    
    for(int i = A.length - 1; i >= 0; i--){
      int pos = Arrays.binarySearch(A2, A1[i]);
      if(pos >= 0){
        while(pos < A.length && A2[pos] == A1[i]){
          pos++;
        }
        cnt += pos;
      } else{ // element not there
        int insertionPoint = -(pos+1);
        cnt += insertionPoint;
      }
      
    }
    
    long sub = (long)l*((long)l+1)/2;
    cnt = cnt - sub;
              
    if(cnt > 1e7) return -1;
    
    return (int)cnt;
  }
  
  ```
