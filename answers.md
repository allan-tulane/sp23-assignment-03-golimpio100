# CMPS 2200 Assignment 3
## Answers

**Name:**___Griffin Olimpio_


Place all written answers from `assignment-03.md` here for easier grading.






- **b.**
- The work and span of the parens_match_iterative function are both O(n), where n is the length of the input string.

The work recurrence is T(n) = T(n-1) + O(1), since each character of the string is processed once and the parens_update function takes O(1) time. The initial condition is T(0) = O(1), since there are no characters to process in an empty string. Solving this recurrence using telescoping, we get T(n) = T(0) + O(n) = O(n).

The span recurrence is S(n) = S(n-1) + O(1), since each character of the string is processed in order and there are no dependencies between them. The initial condition is S(0) = O(1), since there are no dependencies between characters in an empty string. Solving this recurrence using telescoping, we get S(n) = S(0) + O(n) = O(n).




- **d.**
- The filter operation takes linear time O(n) and produces an output of size m. The map operation is done in parallel, and thus takes O(log m) time. The scan operation is done efficiently in O(log n) time.
Let W(n) and S(n) denote the work and span of the solution, respectively. Then we can express W(n) as follows:
W(n) = W(n/2) + O(n) + O(m) + O(log m)
     = W(n/2) + O(n)
The first term corresponds to the recursive call on the left half of the input, and the second term corresponds to the work done at the current level, which consists of a filter, a map, and a scan. Since we assume that the map is done in parallel, we don't need to account for its time in the recurrence.
Using the Master Theorem, we can solve this recurrence to obtain:
W(n) = O(n log n)
Next, we can express S(n) as follows:
S(n) = S(n/2) + O(log n) + O(log m)
     = S(n/2) + O(log n)
The first term corresponds to the span of the recursive call on the left half of the input, and the second term corresponds to the span of the work done at the current level, which consists of a filter, a map, and a scan.
Using the Master Theorem, we can solve this recurrence to obtain:
S(n) = O(log^2 n)
Therefore, the work and span of the solution are O(n log n) and O(log^2 n), respectively.





- **f.**
- Work: 
T(n) = T(n/2) + T(n/2) + O(n)
This recurrence is based on the fact that the algorithm is recursively dividing the input array in half until the base case is reached. In each recursive call, it performs a constant amount of work O(n), so the total work can be expressed as the sum of work done in all recursive calls plus the work done outside of the recursive calls.
The solution for the above recurrence relation is O(n log n).
Span: 
T(n) = T(n/2) + O(1)
In each recursive call, the algorithm performs a constant amount of work O(1), so the span can be expressed as the maximum depth of the recursion tree.
The solution for the above recurrence relation is O(log n).
