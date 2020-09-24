# 104 Maximum Depth of Binary Tree
## Problem Description
https://leetcode.com/problems/maximum-depth-of-binary-tree/

## Solution: Recusion
### Python 3
```
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        if not root:
            return 0
        
        left = self.maxDepth(root.left)
        right = self.maxDepth(root.right) 
        return max(left, right) + 1
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)