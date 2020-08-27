# 268 Missing Number

## Problem Description
https://leetcode.com/problems/missing-number/

## Solution 1: Sorting
### Python 3
```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        nums.sort()
        
        # ensure n is at the last index
        if nums[-1] !=len(nums):
          return len(nums)
        # ensure 0 is at the first index
        elif nums[0] != 0:
          return 0
        
        # otherwise, the missing number is in the range (0, n)
        for i in range(1, len(nums)):
          expected_num = nums[i-1] + 1
          if nums[i] != expected_num:
            return expected_num
```
### Complexity Analysis
- Time complexity: O(nlogn)
- Space complexity: O(1) for in place sorting; O(n) if modifying `nums` is forbidden

## Solution 2: HashSet

### Python 3
```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        nums_set = set(nums)
        n = len(nums) + 1
        for number in range(n):
            if number not in nums_set:
                return number
```

### Java
```
class Solution {
    public int missingNumber(int[] nums) {
        Set<Integer> nums_set = new HashSet<Integer>();
        for (int num : nums) nums_set.add(num);
        
        int n = nums.length + 1;
        for (int number = 0; number < n; number++){
            if(!nums_set.contains(number)) {
                return number;
            }
        }
        return -1;
    }
}
```
### Complexity Analysis
- Time complexity: O(n)
    - the main loop runs in O(n) time
    - creating `nums_set` and inserting elements costs O(n)
    - overall runtime O(n + n) -> O(n)
- Space complexity: O(n)