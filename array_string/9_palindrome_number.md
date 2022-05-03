# [Easy] 9. Palindrome Number

## Question

[[Easy] 9. Palindrome Number](https://leetcode.com/problems/palindrome-number/)

## Thought

轉換成字串後做判斷。

## Code

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        text = str(x)
        return text == text[::-1]
```
