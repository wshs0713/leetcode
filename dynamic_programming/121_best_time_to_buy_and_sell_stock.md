# [Easy] 121. Best Time to Buy and Sell Stock

## Question

[\[Easy\] 121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

## Thought

以兩個指標(`left` and `right`)紀錄買入及賣出 index, 計算利潤及找出最大獲利值。

## Code

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        left, right = 0, 1
        length = len(prices)
        max_profit = 0
        
        while right < length:
            profit = prices[right] - prices[left]
            
            if profit > 0:
                max_profit = max(max_profit, profit)
            else:
                left = right
            right += 1

        return max_profit
```
