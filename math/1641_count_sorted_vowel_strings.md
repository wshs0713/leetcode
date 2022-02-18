# [Medium] 1641. Count Sorted Vowel Strings

## Question

[[Medium] 1641. Count Sorted Vowel Strings](https://leetcode.com/problems/count-sorted-vowel-strings/)

## Thought

排列組合，從 5 個字母中選出 n 個元素，n 個元素可以重複出現，公式: `H5選n = C(5+n-1)選(5-1) = (n+4)!/4!n!`

## Code

```python
class Solution:
    def countVowelStrings(self, n: int) -> int:
        return int((n+4) * (n+3) * (n+2) * (n+1) / 24)
```
