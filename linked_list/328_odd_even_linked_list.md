# [Medium] 328. Odd Even Linked List

## Question

[[Medium] 328. Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/)

## Thought

分別使用兩個指標紀錄 odd and even list, 另外使用 `even_head` 紀錄 even list head, 最後將 odd list next 指向 `even_head`.

## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def oddEvenList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head:
            return

        odd = head
        even = head.next
        even_head = even
        
        while even and even.next:
            odd.next = even.next
            odd = odd.next
            even.next = odd.next
            even = even.next
            
        odd.next = even_head
        return head
```
