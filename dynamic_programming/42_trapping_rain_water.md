# [Hard] 42. Trapping Rain Water

## Question

[[Hard] 42. Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)

## Thought

## Code

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        area = 0
        left_max, right_max = 0, 0
        left, right = 0, len(height)-1
        
        while left < right:
            if height[left] < height[right]:
                if height[left] >= left_max:
                    left_max = height[left]
                else:
                    area += left_max - height[left]
                
                left += 1
            else:
                if height[right] >= right_max:
                    right_max = height[right]
                else:
                    area += right_max - height[right]
                    
                right -= 1
                
        return area
```
