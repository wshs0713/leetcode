# \[Easy\] 53. Maximum Subarray

## Question

[\[Easy\] 53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

## Thought

Dynamic programming

## Code

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        for i in range(1, len(nums)):
            nums[i] = max(nums[i] + nums[i-1], nums[i])
 
        return max(nums)
```
