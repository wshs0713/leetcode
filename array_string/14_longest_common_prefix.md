# 14. Longest Common Prefix

## Question

[14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

## 思考

以第一個字串作為 longest prefix 依序往後比較

## Code

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if len(strs) == 1:
            return strs[0]
        
        if '' in strs:
            return ''
        
        prefix = strs[0]
        i = 1
        
        while (i < len(strs)):
            while (not strs[i].startswith(prefix)):
                prefix = prefix[:-1]
            i += 1

        return prefix
```
