# [Medium] 287. Find the Duplicate Number

## Question

[[Medium] 287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

## Thought

使用 `set()` 紀錄已出現過的 number.

## Code

```python
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        seen = set()
        
        for n in nums:
            if n in seen:
                return n
            seen.add(n)
```
