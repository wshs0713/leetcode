# 13. Roman to Integer

## Question

[Roman to Integer](https://leetcode.com/problems/roman-to-integer/)

## 想法

一次看兩個字元 (`i`, `i+1`)，若 `i+1` 轉換為數字後大於 `i` 轉換為數字，則使用減法，其他情況則是相加。

## Code

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        mapping = {
            'I': 1,
            'V': 5,
            'X': 10,
            'L': 50,
            'C': 100,
            'D': 500,
            'M': 1000
        }

        i = 0
        result = 0

        while i < (length := len(s)):
            if i < length - 1 and mapping[s[i+1]] > mapping[s[i]]:
                result += mapping[s[i+1]] - mapping[s[i]]
                i += 1
            else:
                result += mapping[s[i]]

            i += 1

        return result
```
