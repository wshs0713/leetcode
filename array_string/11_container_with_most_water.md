# [Medium] 11. Container With Most Water

## Question

[[Medium] 11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/)

## Thought

使用 two pointer 解。

## Code

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        left = 0
        right = len(height) - 1
        max_area = 0
        
        while left < right:
            area = min(height[left], height[right]) * (right - left)
            max_area = max(area, max_area)
            
            if height[left] < height[right]:
                left += 1
            else:
                right -= 1
                
        return max_area
```