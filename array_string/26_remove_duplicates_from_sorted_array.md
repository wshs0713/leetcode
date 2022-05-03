# [Easy] 26. Remove Duplicates from Sorted Array

## Question

[[Easy] 26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## Thought

## Code

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        i = 1
        prev_index = 0
        previous = nums[0]
        
        while previous != nums[-1]:
            if nums[i] != previous:
                previous = nums[i]
                nums[prev_index + 1] = nums[i]
                prev_index += 1

            i += 1
            
        return prev_index + 1
```
