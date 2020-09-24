# 111 Minimum Depth of Binary Tree
## Problem Description:
https://leetcode.com/problems/minimum-depth-of-binary-tree/


## Solution 1: DFS
### Python 3
```
class Solution:
    def minDepth(self, root: TreeNode) -> int:
        if not root:
            return 0
        
        children = [root.left, root.right]
        if not any(children):
            return 1
        
        min_depth = float('inf')
        for c in children:
            if c:
                min_depth = min(self.minDepth(c), min_depth)
        return min_depth + 1
```

## Solution 2: BFS
### Python 3
```
class Solution:
    def minDepth(self, root: TreeNode) -> int:
        if not root:
            return 0
        else:
            node_deque = deque([(1, root),])
            
        while node_deque:
            depth, root = node_deque.popleft()
            children = [root.left, root.right]
            if not any (children):
                return depth
            for c in children:
                if c:
                    node_deque.append((depth + 1, c))
```