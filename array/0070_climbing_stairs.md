# 70 Climbing Stairs
## Problem Description
https://leetcode.com/problems/climbing-stairs/

## Solution: Dynamic Programming

One can reach the $i^{th}$ step in one of the two ways:
- taking a single step from $(i-1)^{th}$ step
- taking two steps from $(i-2)^{th}$ step

Let $f(i)$ denotes the number of ways to reach to the $i^{th}$ step:

$f(i) = f(i-1) + f(i-2)$

### Python 3
```
class Solution:
    def climbStairs(self, n: int) -> int:
        f = [1, 1] # f(0)=1, f(1)=1
        for i in range(2, n+1):
            f.append(f[i-1] + f[i-2])
        return f[n]
```

### Java
```
class Solution{
    public int climbStairs(int n){
        int[]f = new int[n + 1];
        f[0] = 1;
        f[1] = 1;
        for(int i = 2; i <= n; i++){
            f[i] = f[i - 1] + f[i - 2];
        }
        return f[n];
    }
}
```
### Complexity analysis
- Time complexity: O(n)
- Space complexity: O(n)
### Visualization of the code (Python)
[link](http://www.pythontutor.com/visualize.html#code=def%20climbStairs%28n%29%3A%0A%20%20%20%20f%20%3D%20%5B1,%201%5D%0A%20%20%20%20for%20i%20in%20range%282,%20n%20%2B%201%29%3A%0A%20%20%20%20%20%20%20%20f.append%28f%5Bi-1%5D%20%2B%20f%5Bi-2%5D%29%0A%20%20%20%20return%20f%5Bn%5D%0A%0An%20%3D%205%0AclimbStairs%28n%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)