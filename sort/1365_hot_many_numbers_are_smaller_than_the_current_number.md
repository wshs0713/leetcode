# [Easy] 1365. How Many Numbers Are Smaller Than the Current Number

## Question

[[Easy] 1365. How Many Numbers Are Smaller Than the Current Number](https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/)

## Thought

以另一個 array 儲存排序後的結果，再將原本 `nums` 中的每個 item 對應到 sorted array 的 index 存到 result, 即為所求的答案。

## Code

```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        sort_list = sorted(nums)
        result = []
        
        for item in nums:
            result.append(sort_list.index(item))
            
        return result
```
