# \[Easy\] 28. Implement strStr()

## Question

[\[Easy\] 28. Implement strStr()](https://leetcode.com/problems/implement-strstr/)

## Thought

1. 使用 Python `str.index()` 即可
2. 從 haystack 依序比對 needle 字串，若比對成功，回傳該 index 即可

## Code

- 使用 Python `str.index()`

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        index = -1
        if needle in haystack:
            index = haystack.index(needle)
        return index
```

- 從 haystack 依序比對 needle 字串，若比對成功，回傳該 index 即可

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        index = -1
        len_h = len(haystack)
        len_n = len(needle)

        for i in range(0, len_h-len_n+1):
            if haystack[i:i+len_n] == needle:
                return i
        return index
```
