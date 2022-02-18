# [Medium] 5. Longest Palindromic Substring

## Question

[[Medium] 5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)

## Thought

用兩個指標解此問題，時間複雜度：`O(n^2)`，空間複雜度 `O(1)`。

## Code

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        if len(s) == 1:
            return s
        
        result = ''
        max_length = 0
        
        for i in range(len(s)):
            is_palindromic = False
            
            for j in range(i+1, len(s)+1):
                if s[i:j] == ''.join(reversed(s[i:j])):
                    if j - i > max_length:
                        result = s[i:j]
                        max_length = j - i
                    
        return result
```
