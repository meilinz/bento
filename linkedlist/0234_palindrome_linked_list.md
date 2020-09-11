# 234 Palindrome Linked List

## Problem Description
https://leetcode.com/problems/palindrome-linked-list/

## Solution: Copy into Array List and then Compare
### Python 3
```
class Solution:
    def isPalindrome(self, head: ListNode) -> bool:
        vals = []
        current_node = head
        while current_node is not None:
            vals.append(current_node.val)
            current_node = current_node.next
        
        return vals == vals[::-1]
```

### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)