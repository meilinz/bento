# 303 Range Sum Query
## Problem Description
https://leetcode.com/problems/range-sum-query-immutable/

## Solution: Caching
- pre-compute the cummulative sum from index to 0 to k. 
- derive `sum(i,j)` from `sum[k]`, let sum[k] be the cumulative sum for nums[0, k-1] (inclusive)
$$ sumRange(i,j) = sum[j + 1] - sum[i]$$

### Java
```
class NumArray {
    private int[] sum;
    public NumArray(int[] nums) {
        sum = new int[nums.length + 1];
        for (int i = 0; i < nums.length; i++) {
            sum[i + 1] = sum[i] + nums[i];
        }
    }

public int sumRange(int i, int j) {
    return sum[j + 1] - sum[i];
    }
}

/**
 * Your NumArray object will be instantiated and called as such:
 * NumArray obj = new NumArray(nums);
 * int param_1 = obj.sumRange(i,j);
 */
```

### Python 3
```
class NumArray:

    def __init__(self, nums: List[int]):
        self.sum = collections.defaultdict(int)
        for i in range(len(nums)):
            self.sum[i] = nums[i] + self.sum[i-1]
            print(self.sum)

    def sumRange(self, i: int, j: int) -> int:
        return self.sum[j] - self.sum[i-1]
```