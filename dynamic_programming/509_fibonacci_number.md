# [Easy] 509. Fibonacci Number

## Question

[\[Easy\] 509. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)

## Thought

Dynamic programming, array 中的每一個 element 紀錄前面 `f(n-1) + f(n-2)` 的值，最後回傳 `f(n)`。

## Code

```python
class Solution:
    def fib(self, n: int) -> int:
        dp = [0, 1]

        if n < 2:
            return dp[n]

        dp += [0] * (n-1)

        for i in range(2, n+1):
            dp[i] = dp[i-1] + dp[i-2]

        return dp[n]
```
