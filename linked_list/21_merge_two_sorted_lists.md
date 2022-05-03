# [Easy] 21. Merge Two Sorted Lists

## Question

[[Easy] 21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)

## Thought

## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        result = ListNode(0)
        current = result
        
        l1 = list1
        l2 = list2
        
        while l1 and l2:
            if l1.val <= l2.val:
                current.next = ListNode(l1.val)
                current = current.next
                l1 = l1.next
            else:
                current.next = ListNode(l2.val)
                current = current.next
                l2 = l2.next
                
        if l1:
            current.next = l1
        if l2:
            current.next = l2
            
        return result.next
```
