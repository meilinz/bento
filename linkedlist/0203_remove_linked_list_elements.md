# 203 Remove Linked List Elements
## Problem Description
https://leetcode.com/problems/remove-linked-list-elements/

## Solution
### Python 3
```
class Solution:
    def removeElements(self, head: ListNode, val: int) -> ListNode:
        while head is not None and head.val == val:
            head = head.next
        
        current_node = head
        while current_node is not None and current_node.next is not None:
            if current_node.next.val == val:
                current_node.next = current_node.next.next
            else:
                current_node = current_node.next
        
        return head
```

### Java
```
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        while (head != null && head.val == val) {
            head = head.next;
        }
        
        ListNode current_node = head;
        while (current_node != null && current_node.next != null) {
            if (current_node.next.val == val) {
                current_node.next = current_node.next.next;
            } else {
                current_node = current_node.next;
            }
        }
        return head;
    }
}
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)