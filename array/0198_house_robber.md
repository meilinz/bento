# 198 House Robber
## Problem description: 
https://leetcode.com/problems/house-robber/

## Solution: Dynamic Programming

Start from the simplest case. Let

$f(i)=$ largest amount that you can rob from the first $i$ houses

$a_i$ = amount of money at the $i^{th}$ house

For $n=1$, $f(1) = a_1$;

For $n=2$, $f(2) = Max(a_1, a_2)$;

For $n=3$, you have two options: 
- rob the third house, and add this to the first house
- do not rob the third  house, and stick to the largest amount you of the first two hourse

 $f(3) = Max(f(1) + a_3, f(2))$
 
 More generally, for $i > 2$:
 
 $f(i) = Max(f(i-2) + a_i, f(i-1))$
 
### Python 3
```
class Solution:
	def rob(self, nums: List[int]) -> int:
    	if len(nums) == 0:
            return 0
        if len(nums) == 1:
            return nums[0]
        if len(nums) == 2:
            return max(nums[0],nums[1])
        
        dp = [0] * len(nums)
        dp[0] = nums[0]
        dp[1] = max(nums[0], nums[1])
        for i in range(2, len(nums)):
            dp[i] = max(dp[i-2] + nums[i], dp[i-1])
            
        return dp[len(nums)-1]
```

### Java
```
class Solution {
    public int rob(int[] nums) {
        if(nums.length == 0) {
           return 0;
       }
        if(nums.length == 1) {
            return nums[0];
        }
        if(nums.length == 2) {
            return Math.max(nums[0], nums[1]);
        }
        
        int[] dp = new int[nums.length];
        dp[0] = nums[0];
        dp[1] = Math.max(nums[0], nums[1]);
        for(int i = 2; i < dp.length; i++) {
            dp[i] = Math.max(dp[i - 2] + nums[i], dp[i - 1]);
        }
        
        return dp[nums.length - 1];
    }
}
```

### Complexity Analysis
- Time complexity: O(n)
- Space complexity:O(1)

### Visualization of the code (Python): [link](http://www.pythontutor.com/visualize.html#code=def%20rob%28nums%29%3A%0A%20%20%20%20if%20len%28nums%29%20%3D%3D%200%3A%0A%20%20%20%20%20%20%20%20return%200%0A%20%20%20%20if%20len%28nums%29%20%3D%3D%201%3A%0A%20%20%20%20%20%20%20%20return%20nums%5B0%5D%0A%20%20%20%20if%20len%28nums%29%20%3D%3D%202%3A%0A%20%20%20%20%20%20%20%20return%20max%28nums%5B0%5D,nums%5B1%5D%29%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20dp%20%3D%20%5B0%5D%20*%20len%28nums%29%0A%20%20%20%20dp%5B0%5D%20%3D%20nums%5B0%5D%0A%20%20%20%20dp%5B1%5D%20%3D%20max%28nums%5B0%5D,%20nums%5B1%5D%29%0A%20%20%20%20for%20i%20in%20range%282,%20len%28nums%29%29%3A%0A%20%20%20%20%20%20%20%20dp%5Bi%5D%20%3D%20max%28dp%5Bi-2%5D%20%2B%20nums%5Bi%5D,%20dp%5Bi-1%5D%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%20%20return%20dp%5Blen%28nums%29-1%5D%0A%20%20%20%20%0Anums%20%3D%20%5B2,7,9,3,1%5D%0Arob%28nums%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)