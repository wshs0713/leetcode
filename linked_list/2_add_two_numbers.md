# [Medium] 2. Add Two Numbers

## Question

[[Medium] 2. Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)

## Thought

## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        result = ListNode(0)
        current = result
        carry = 0
        
        while l1 or l2:
            total = 0
            
            if l1:
                total += l1.val
                l1 = l1.next
            if l2:
                total += l2.val
                l2 = l2.next
                
            total += carry
            current.next = ListNode(total%10)
            current = current.next
            carry = total // 10
            
        if carry:
            current.next = ListNode(carry)
            
        return result.next
```
