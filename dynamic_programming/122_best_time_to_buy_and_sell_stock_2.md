# [Medium] 122. Best Time to Buy and Sell Stock II

## Question

[\[Medium\] 122. Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

## Thought

以 `max_profit` 記錄每次買賣所獲得的累計利潤，最後回傳該值。

## Code

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_profit = 0
        
        for i in range(1, len(prices)):
            if prices[i] > prices[i-1]:
                max_profit += prices[i] - prices[i-1]
                
        return max_profit
```
