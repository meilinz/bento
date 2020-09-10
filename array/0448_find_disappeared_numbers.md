# 448 Find All Numbers Disappered in an Array
## Problem Description
https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/

## Solution 1: Hash Map
### Python 3
```
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        
        hash_table = {}
        result = []
        
        for num in nums:
          hash_table[num] = 1
        
        for num in range(1, len(nums) + 1):
          if num not in hash_table:
            result.append(num)
        
        return result
```
### Complexity Analysis 
- Time comlexity: O(N)
- Space complexity: O(N)

## Solution 2: Set Operation
### Python 3
```
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        nums_set = set(nums)
        ideal_set = set(range(1, len(nums) + 1))
        
        missing_set = ideal_set.difference(nums_set)
        result = list(missing_set)
        
        return result
```
### Complexity Analysis 
- Time comlexity: O(N)
- Space complexity: O(N)