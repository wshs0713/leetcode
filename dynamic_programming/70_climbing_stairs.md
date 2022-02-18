# [Easy] 70. Climbing Stairs

## Question

[[Easy] 70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

## Thought

Dynamic programming, 基本上也是一個 fibonacci, array 中的每一個 element 紀錄前面 `f(n-1) + f(n-2)` 的值，最後回傳 `f(n)`。

## Code

```python
class Solution:
    def climbStairs(self, n: int) -> int:
        dp = [0, 1, 2]
        
        if n < 3:
            return dp[n]
        
        dp += [0] * (n-2)
        
        for i in range(3, n+1):
            dp[i] = dp[i-1] + dp[i-2]
            
        return dp[n]
```
