# [Easy] 53. Maximum Subarray

## Question

[[Easy] 53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

## Thought

Dynamic programming, array 中的每一個 element 紀錄前面 subarray 總和最大值，最後再取 array 中的最大值。

## Code

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        dp = nums
        
        for i in range(1, len(nums)):
            dp[i] = max(dp[i-1]+dp[i], dp[i])
            
        return max(dp)
```
