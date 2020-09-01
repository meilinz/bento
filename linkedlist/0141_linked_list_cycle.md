# 141 Linked List Cycle
## Problem Description
https://leetcode.com/problems/linked-list-cycle/

## Solution 1: Hash Table
### Python 3
```
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        dictionary = {}
        while head:
            if head in dictionary: 
                return True
            else: 
                dictionary[head]= True
            head = head.next
        return False
```

### Java
```
public class Solution {
    public boolean hasCycle(ListNode head) {
        Set<ListNode> nodesSeen = new HashSet<>();
        while (head != null) {
            if (nodesSeen.contains(head)) {
                return true;
            } else {
                nodesSeen.add(head);
            }
            head = head.next;
        }
        return false;
    }
}
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)

## Solution 2: Two Pointers
### Python 3
```
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        if not head:
            return False
        slow = head
        fast = head.next
        while slow != fast:
            if not fast or not fast.next:
                return False
            slow = slow.next
            fast = fast.next.next
        return True
```
### Java
```
public class Solution {
    public boolean hasCycle(ListNode head) {
        if (head == null || head.next == null) {
            return false;
        }
        ListNode slow = head;
        ListNode fast = head.next;
        while (slow != fast) {
            if (fast == null || fast.next == null) {
                return false;
            }
            slow = slow.next;
            fast = fast.next.next;
        }
        return true;
    }
}
```

### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)