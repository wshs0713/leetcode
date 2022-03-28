# [Easy] 20. Valid Parentheses

## Question

[[Easy] 20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

## Thought

以 stack 實作，若 character is `(`, `[`, `{` push to stack, 若 character is `)`, `]`, `}` 則檢查 stack:

- 若 stack 為空, return False
- stack 最後一個 element 是否為對應的符號, 若是則 pop 出 stack, 若不是則 return False.

依序檢查至字串結束，最後回傳 stack 是否為空。

## Code

```python
class Solution:
    def isValid(self, s: str) -> bool:
        mapping = {
            ')': "(",
            ']': '[',
            '}': '{'
        }

        left = ['(', '[', '{']
        stack = []
        
        for item in s:
            if item in left:
                stack.append(item)
            elif len(stack) == 0:
                return False
            elif mapping[item] == stack[-1]:
                stack.pop()
            else:
                return False
        
        return len(stack) == 0
```
