# [leetcode-largest-perimeter-triangle](https://leetcode.com/problems/largest-perimeter-triangle/solution/)

Given an integer array `nums`, return *the largest perimeter of a triangle with a non-zero area, formed from three of these lengths*.  If it is impossible to form any triangle of a non-zero area, return `0`.

**Example 1:**
```
Input: nums = [2,1,2]
Output: 5
```

**Example 2:***
```
Input: nums = [1,2,1]
Output: 0
```

**Constraints:**
- `3 <= nums.length <= 10^4` 
- `1 <= nums[i] <= 10^6`

## Approach
### Intuition
Without loss of generality, say the sidelengths of the triangle are `a <= b <= c`.  The necessary and sufficient condition for these lengths to form a triangle of non-zero area is `a + b > c`.

Say we knew `c` already.  There is no reason not to choose the largest possible `a` and `b` from the array.  If `a + b > c`, then it forms a triangle, otherwise it doesn't.

### Algorithm
This leads to a simple algorithm: Sort the array.  For any `c` in the array, we choose the largest possible `a <= b <= c`: these are just hte two values adjacent to `c`.  If this forms a triangle, we return the answer.

### Complexity Analysis
- Time Complexity: `O(N log N)`, where `N` is the length of `A`.
- Space Complexity: `O(1)`.

