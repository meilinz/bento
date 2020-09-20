# 704 Binary Search

## Problem Description:
https://leetcode.com/problems/binary-search/

## Solution
### Python 3
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            elif target < nums[mid]:
                right = mid - 1
            else:
                left = mid + 1
        
        return -1
```

### Complexity Analysis
- Time complexity: O(logN)
- Space complexity: O(1)