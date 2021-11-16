# \[Easy\] 14. Longest Common Prefix

## Question

[\[Easy\] 14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

## Thought

以 `strs` 中最短的字串作為 longest prefix 依序比較每個 element.

## Code

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if not strs or len(strs) == 0 or '' in strs:
            return ''

        if len(strs) == 1:
            return strs[0]
        
        prefix = min(strs, key=len)
        i = 0
        
        while (i < len(strs)):
            while (not strs[i].startswith(prefix)):
                prefix = prefix[:-1]
            i += 1

        return prefix
```
