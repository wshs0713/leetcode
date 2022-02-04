# [Medium] 983. Minimum Cost For Tickets

## Question

[\[Medium\] 983. Minimum Cost For Tickets](https://leetcode.com/problems/minimum-cost-for-tickets/)

## Thought

Dynamic programming, array 中的每一個 element 紀錄該天所需花費的最低票價。

## Code

```python
class Solution:
    def mincostTickets(self, days: List[int], costs: List[int]) -> int:
        if not days:
            return 0
        
        dp = [0] + [float('inf')] * 365
        
        for day in range(1, len(dp)):
            if day not in days:
                dp[day] = dp[day-1]
                continue
                
            one_day_pass = dp[day-1] + costs[0]
            seven_day_pass = dp[day-7] + costs[1] if day >= 7 else costs[1]
            thirty_day_pass = dp[day-30] + costs[2] if day >= 30 else costs[2]
                
            dp[day] = min(one_day_pass, seven_day_pass, thirty_day_pass)
            
        return dp[-1]
```
