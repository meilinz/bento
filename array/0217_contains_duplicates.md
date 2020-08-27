# 217 Contains Duplicates

## Problem Description
https://leetcode.com/problems/contains-duplicate/

## Solution 1: using dictionary
### Python 3
```
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
      duplicates = {}
      for i in nums:
        if i in duplicates:
          return True
        else:
          duplicates[i] = 1
      return False
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)

## Solution 2: using set
### Python 3
```
 class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        s = set(nums)
        if len(s) == len(nums):
            return False
        else:
            return True
```
### Java
```
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> set = new HashSet();
        
        for (int i:nums){
            set.add(i);
        }
        if (set.size() == nums.length){
            return false;
        } else {
            return true;
        }
    }
}
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)