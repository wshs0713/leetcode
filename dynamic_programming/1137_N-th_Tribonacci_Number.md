# [Easy] 1137. N-th Tribonacci Number

## Question

[\[Easy\] 1137. N-th Tribonacci Number](https://leetcode.com/problems/n-th-tribonacci-number/)

## Thought

Dynamic programming, array 中的每一個 element 紀錄前面 `f(n-1) + f(n-2) + f(n-3)` 的值，最後回傳 `f(n)`。

## Code

```python
class Solution:
    def tribonacci(self, n: int) -> int:
        dp = [0, 1, 1]
        if n < 3:
            return dp[n]

        dp += [0] * (n-2)

        for i in range(3, n+1):
            dp[i] = dp[i-1] + dp[i-2] + dp[i-3]

        return dp[n]
```
