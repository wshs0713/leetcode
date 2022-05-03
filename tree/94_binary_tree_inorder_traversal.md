# [Easy] 94. Binary Tree Inorder Traversal

## Question

[[Easy] 94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)

## Thought

Inorder traversal: left -> root -> right

## Code

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        result = []
        
        if not root:
            return result
        
        def traversal(node: TreeNode):
            if not node:
                return
        
            traversal(node.left)
            result.append(node.val)
            traversal(node.right)
        
        traversal(root)
        return result
```
