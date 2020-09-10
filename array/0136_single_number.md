# 136 Single Number
## Problem Description
https://leetcode.com/problems/single-number/

## Solution 1: Hash table
### Python 3
```
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        hash_table = {}
        
        for num in nums:
            if num not in hash_table:
                hash_table[num] = 1
            else:
                hash_table[num] += 1
        
        for num in hash_table:
            if hash_table[num] == 1:
                return num
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)