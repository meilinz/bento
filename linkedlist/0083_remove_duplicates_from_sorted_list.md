# 83 Remove Duplicates from Sorted List
## Problem Description
https://leetcode.com/problems/remove-duplicates-from-sorted-list/

## Solution
### Python 3
```
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        current = head
        while current is not None and current.next is not None:
            if current.next.val == current.val:
                current.next = current.next.next
            else:
                current = current.next
        
        return head
```

### Java
```
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode current = head;
        while (current != null && current.next != null) {
            if (current.next.val == current.val) {
                current.next = current.next.next;
            } else {
                current = current.next;
            }
        }
        return head;
    }
}
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)