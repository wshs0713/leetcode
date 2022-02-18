# [Easy] 1. Two Sum

## Question

[[Easy] 1. Two Sum](https://leetcode.com/problems/two-sum/)

## Thought

以 dictionary 紀錄每個數字對應的 index, 再列舉每個 num, 檢查差值是否有在 dictionary 中，若有即回傳對應 index.

## Code

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        mapping = {}
        
        for index, num in enumerate(nums):
            diff = target - num
            
            if diff in mapping:
                return [mapping[diff], index]
            
            mapping[num] = index
```
