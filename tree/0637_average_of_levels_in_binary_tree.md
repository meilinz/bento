# 637 Average of Levels in Binary Tree

## Problem Description:
https://leetcode.com/problems/average-of-levels-in-binary-tree/
## Solution: BFS
### Python 3
```
class Solution:
    def averageOfLevels(self, root: TreeNode) -> List[float]:
        levels = []
        next_level = deque([root])
        
        while root and next_level:
            curr_level = next_level
            next_level = deque()
            levels.append([])
            
            for node in curr_level:
                levels[-1].append(node.val)
                if node.left:
                    next_level.append(node.left)
                if node.right:
                    next_level.append(node.right)
                    
        levels_sums = [sum(x)/len(x) for x in levels]
        return levels_sums
```
## Complexity Analysis
- Time Complexity: O(n)
- Space Complexity: 