# 704 Binary Search

## Problem Description:
https://leetcode.com/problems/binary-search/

## Solution 1: Iteration
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

## Solution 2: Recursion
### Python 3
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        
        return self.recursive_search(nums, 0, len(nums) - 1, target)
    
    def recursive_search(self, nums, left, right, target):
        if left > right:
            return -1
        
        mid = (left + right) // 2
        if target < nums[mid]:
            return self.recursive_search(nums, left, mid - 1, target)
        
        if target > nums[mid]:
            return self.recursive_search(nums, mid + 1, right, target)
        
        return mid
```

### Complexity Analysis
- Time complexity: O(logN)
- Space complexity: O(logN)