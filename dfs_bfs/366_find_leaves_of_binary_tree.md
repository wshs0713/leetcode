# [Medium] 366. Find Leaves of Binary Tree

## Question

[[Medium] 366. Find Leaves of Binary Tree](https://leetcode.com/problems/find-leaves-of-binary-tree/)

## Thought

## Code

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def findLeaves(self, root: Optional[TreeNode]) -> List[List[int]]:
        result = []
        
        def dfs(node):
            if not node:
                return -1
            
            height = max(dfs(node.left), dfs(node.right)) + 1
            
            if height >= len(result):
                result.append([])
                
            result[height].append(node.val)
            return height

        dfs(root)
        return result
```
