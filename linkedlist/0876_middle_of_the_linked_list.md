# 876 Middle of the Linked List

## Problem Description
https://leetcode.com/problems/middle-of-the-linked-list/

## Solution 1: Output to Array
### Python 3
```
class Solution:
    def middleNote(self, head: ListNode) -> ListNode:
        arrayA[head]
        while arrayA[-1].next:
            arrayA.append(arrayA[-1].next)
        return arrayA[len(arrayA) // 2]
```

### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(n)

## Solution 2: Fast and Slow Pointers
### Python 3
```
class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        return slow
```
### Java
```
class Solution {
    public ListNode middleNode(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }  
}
```
### Complexity Analysis
- Time complexity: O(n)
- Space complexity: O(1)