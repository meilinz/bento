# 107 Binary Tree Level Order Traversal II

## Problem Description:
https://leetcode.com/problems/binary-tree-level-order-traversal-ii/

## Solution 1: BFS Traversal
### Python 3
```
class Solution:
    def levelOrderBottom(self, root: TreeNode) -> List[List[int]]:
        levels = []
        next_level = deque([root])
        
        while root and next_level:
            current_level = next_level
            next_level = deque()
            levels.append([])
            
            for node in current_level:
                levels[-1].append(node.val)
                if node.left:
                    next_level.append(node.left)
                if node.right:
                    next_level.append(node.right)
        
        return levels[::-1]
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)