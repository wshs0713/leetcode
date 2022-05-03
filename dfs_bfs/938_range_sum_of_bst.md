# [Easy] 938. Range Sum of BST

## Question

[[Easy] 938. Range Sum of BST](https://leetcode.com/problems/range-sum-of-bst/)

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
    def rangeSumBST(self, root: Optional[TreeNode], low: int, high: int) -> int:
        def dfs(node: TreeNode):
            if node:
                if low <= node.val <= high:
                    self.result += node.val

                if node.val > low:
                    dfs(node.left)

                if node.val < high:
                    dfs(node.right)
                
        self.result = 0
        dfs(root)
        return self.result
```
