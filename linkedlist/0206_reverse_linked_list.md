# 206 Reverse Linked List
## Problem Description
https://leetcode.com/problems/reverse-linked-list/

## Solution
### Python 3
```
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        current = head
        previous = None
        
        while current is not None:
            next_node = current.next
            current.next = previous
            previous = current
            current = next_node
            
        return previous
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)