# [Medium] 3. Longest Substring Without Repeating Characters

## Question

[[Medium] 3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

## Thought

用 sliding window 解。

## Code

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        left = 0
        right = 0
        max_length = 0
        
        while right < len(s):
            if s[right] not in s[left:right]:
                right += 1
                max_length = max(max_length, right-left)
            else:
                left += 1
                right -= 1
        
        return max_length
```
