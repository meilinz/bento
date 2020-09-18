# 21 Merge Two Sorted List
## Problem Description
https://leetcode.com/problems/merge-two-sorted-lists/

## Solution 1: Iteration
### Python 3
```
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        prehead = ListNode(-1)
        prev = prehead
        
        while l1 is not None and l2 is not None:
            if l1.val <= l2.val:
                prev.next = l1
                l1 = l1.next
            else:
                prev.next = l2
                l2 = l2.next
            prev = prev.next
            
        prev.next = l1 if l1 is not None else l2
        
        return prehead.next
 ```
 
### Java
```
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode prehead = new ListNode(-1);
        ListNode prev = prehead;
        
        while (l1 != null && l2 != null) {
            if (l1.val <= l2.val){
                prev.next = l1;
                l1 = l1.next;
            } else {
                prev.next = l2;
                l2 = l2.next;
            }
            prev = prev.next;
        }
        prev.next = l1 != null ? l1 : l2;
        
        return prehead.next;
    }
}

```

### Complexity Analysis
 - Time complexity: O(n + m)
 - Space complexity: O(1)

## Solution 2: Recursion
### Python 3
 ```
 class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if l1 is None:
            return l2
        elif l2 is None:
            return l1
        elif l1.val < l2.val:
            l1.next = self.mergeTwoLists(l1.next, l2)
            return l1
        else:
            l2.next = self.mergeTwoLists(l1, l2.next)
            return l2

 ```
 
### Complexity Analysis
 - Time complexity: O(n + m)
 - Space complexity: O(n + m)