# [Easy] 338. Counting Bits

## Question

[[Easy] 338. Counting Bits](https://leetcode.com/problems/counting-bits/)

## Thought

依序列值，找規律:

0 -> 0
1 -> 1
2 -> 10
3 -> 11
4 -> 100
5 -> 101
6 -> 110
7 -> 111
8 -> 1000
9 -> 1001
10 -> 1010

dp[0] = 0
dp[1] = 1 = dp[0] + 1 = dp[1&0] + 1
dp[2] = 1 = dp[0] + 1 = dp[2&1] + 1
dp[3] = 2 = dp[2] + 1 = dp[3&2] + 1
dp[4] = 1 = dp[0] + 1 = dp[4&3] + 1
dp[5] = 2 = dp[4] + 1 = dp[5&4] + 1
dp[6] = 2 = dp[4] + 1 = dp[6&5] + 1
dp[7] = 3 = dp[6] + 1 = dp[7&6] + 1
dp[8] = 1 = dp[0] + 1 = dp[8&7] + 1
dp[9] = 2 = dp[8] + 1 = dp[9&8] + 1
dp[10] = 2 = dp[8] + 1 = dp[10&9] + 1

可以推出 `dp[n] = dp[n & (n-1)] + 1`.

## Code

```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        dp = [0] * (n + 1)
        
        for i in range(1, n+1):
            dp[i] = dp[i & (i-1)] + 1
            
        return dp
```
