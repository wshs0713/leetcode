# [Medium] 7. Reverse Integer

## Question

[[Medium] 7. Reverse Integer](https://leetcode.com/problems/reverse-integer/)

## Thought

先將負號另外判斷，接著將 integer 轉為 string 再做反轉，若為負數再加上負號。若超出 32-bit integer range `[-231, 231 - 1]` 則回傳 0.

## Code

```python
class Solution:
    def reverse(self, x: int) -> int:
        low_bound = -1 * (2 ** 31)
        high_bound = (2 ** 31) - 1
        positive = True if x >= 0 else False
        
        strs = str(x) if positive else str(x)[1:]
        result = int(strs[::-1])

        if not positive:
            result = -result
        
        if result < low_bound or result > high_bound:
            return 0

        return result
```
