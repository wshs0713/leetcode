# [Easy] 344. Reverse String

## Question

[[Easy] 344. Reverse String](https://leetcode.com/problems/reverse-string/)

## Thought

使用兩個指標(left, right), 依序交換位置。

## Code

```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        left = 0
        right = len(s)-1
        
        while left < right:
            tmp = s[left]
            s[left] = s[right]
            s[right] = tmp
            
            left += 1
            right -= 1
```
