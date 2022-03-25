# [Medium] 1029. Two City Scheduling

## Question

[[Medium] 1029. Two City Scheduling](https://leetcode.com/problems/two-city-scheduling/)

## Thought

To optimize the total costs, let's sort the persons by `price_A - price_B` and then send the first `n` persons to the city A, and the others to the city B, because this way the company costs are minimal.

## Code

```python
class Solution:
    def twoCitySchedCost(self, costs: List[List[int]]) -> int:
        min_cost = 0
        n = len(costs) // 2
        
        costs.sort(key = lambda cost: cost[0] - cost[1])
        
        for i in range(n):
            min_cost += costs[i][0] + costs[i+n][1]
            
        return min_cost
```
