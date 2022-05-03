# [Hard] 4. Median of Two Sorted Arrays

## Question

[[Hard] 4. Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/)

## Thought

將兩個 array 排序後再找中間值。

## Code

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        sort_list = sorted(nums1 + nums2)
        length = len(sort_list)
        
        if length == 0:
            return 0
        elif length == 1:
            return sort_list[0]
        else:
            mid = length // 2
            
            if length % 2 == 0:
                return (sort_list[mid-1] + sort_list[mid]) / 2
            return sort_list[mid]
```
