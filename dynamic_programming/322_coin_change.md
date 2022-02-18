# [Medium] 322. Coin Change

## Question

[[Medium] 322. Coin Change](https://leetcode.com/problems/coin-change/)

## Thought

## Code

```python
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [-1]*(amount+1)
        
        dp[0] = 0
        for num in range(1, amount+1):
            min_val = 2**31-1

            for coin in coins:
                if num - coin >= 0 and dp[num-coin] != -1:
                    min_val = min(min_val, dp[num-coin]+1)
            
            if min_val == 2**31-1:
                min_val = -1
            dp[num] = min_val
        
        return dp[amount]
```
