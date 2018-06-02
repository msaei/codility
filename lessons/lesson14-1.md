## Lesson 14: Binary search algorithm
## NailingPlanks
link to question: (https://app.codility.com/programmers/lessons/14-binary_search_algorithm/nailing_planks/)
### solution for python(62-100-25)
performance detail:(https://app.codility.com/demo/results/trainingT7PKKB-HHY/)
```
def solution(A, B, C):
    # write your code in Python 3.6
    for i in range(len(C)):
        nail_pos = C[i]
        A, B = remove_nailed_planks(nail_pos, A, B)
        if len(A) == 0:
            return i + 1
    return -1
    pass

# this function should refactor to use binary search instead of going through all planks
def remove_nailed_planks(nail_pos, A, B):
    Edited_A = []
    Edited_B = []
    for i in range(len(A)):
        if nail_pos < A[i] or nail_pos > B[i]:
            #the plank is not under nail
            Edited_A.append(A[i])
            Edited_B.append(B[i])
    return Edited_A, Edited_B
    pass
    
```
### binary search algorithm example  
Problem: You are given n binary values x0, x1, . . . , xn−1, such that xi ∈ {0, 1}. This array
represents holes in a roof (1 is a hole). You are also given k boards of the same size. The goal
is to choose the optimal (minimal) size of the boards that allows all the holes to be covered
by boards.  
Solution: The size of the boards can be found with a binary search. If size x is sufficient to
cover all the holes, then we know that sizes x+ 1, x+ 2, . . . , n are also sufficient. On the other
hand, if we know that x is not sufficient to cover all the holes, then sizes x − 1, x − 2, . . . , 1
are also insufficient.  
There is the question of how to check whether size x is sufficient. We can go through all the
indices from the left to the right and greedily count the boards. We add a new board only if
there is a hole that is not covered by the last board.
The total time complexity of such a solution is O(n log n) due to the binary search time.  
sorce: (https://codility.com/media/train/12-BinarySearch.pdf)
```
def boards(A, k):
    n = len(A)
    beg = 1
    end = n
    result = -1
    while (beg <= end):
        mid = (beg + end) / 2
        if (check(A, mid) <= k):
            end = mid - 1
            result = mid
        else:
            beg = mid + 1
    return result
    
def check(A, k):
    n = len(A)
    boards = 0
    last = -1
    for i in xrange(n):
        if A[i] == 1 and last < i:
            boards += 1
            last = i + k - 1
    return boards
```
### codesays solution(100-100)
link to codesays: (https://codesays.com/2014/solution-to-nailing-planks-by-codility/)
```
def _findFirstNail(plankBegin, plankEnd, nails, preResult):
    # Function: find the nails, that could nail this plank.
    #
    # Input: plankBegin: the begin position of current plank
    #        plankEnd: the end position of current plank
    #        nails: the nails' position and index
    #        preResult: for all of the previous planks, the
    #           first preResult+1 nails in original array
    #           could be sequentially used to nail them.
    #
    # Return: If all these nails are after the preResult's
    #       position, return the first nail's position in
    #       the original nails' array.
    #       Else, return the preResult as the result.
 
    result = -1     # The index of nail in the original array
    resultPos = -1  # The index of nail in the sorted array
 
    nailLower = 0
    nailUpper = len(nails) - 1
    nailMid = 0
 
    # Find the first nail, whose postion >= plankBegin and
    #   position <= plankEnd, with binary search algorithm
    while nailLower <= nailUpper:
        nailMid = (nailLower + nailUpper) // 2
        nailPosMid = nails[nailMid][1]
        if nailPosMid < plankBegin:
            nailLower = nailMid + 1
        elif nailPosMid > plankEnd:
            nailUpper = nailMid - 1
        else:
            nailUpper = nailMid - 1
            result = nails[nailMid][0]
            resultPos = nailMid
 
    # Cannot find one, which could nail the plank
    if result == -1:                        return -1
 
    # Linear search all the quanlified nails, and find
    # out the one with the earliest position.
    resultPos += 1
    while resultPos < len(nails):
        # Not quanlified anymore.
        if nails[resultPos][1] > plankEnd:  break
        result = min(result, nails[resultPos][0])
        resultPos += 1
        # If we find a position before the preResult. We could
        # terminate our search and return.
        # With a position before the preResult, the result for
        # this round must <= preResult. And globally, the final
        # result is the maximum of ALL the results in each rounds.
        # So the result of this round actually does not affect
        # the final result.
        if preResult >= result:             return preResult
 
    return max(result, preResult)
 
def solution(A, B, C):
    # Sort the nails according to their positions
    nails = sorted(enumerate(C), key = lambda x: x[1])
    result = -1
 
    for plankIndex in range(len(A)):
        # Find a nail for the current plank
        result = _findFirstNail(A[plankIndex], B[plankIndex], nails, result)
        if result == -1:  return -1     # Cannot find such a nail
 
    return result + 1
```
