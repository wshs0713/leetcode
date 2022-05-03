# [Medium] 8. String to Integer (atoi)

## Question

[[Medium] 8. String to Integer (atoi)](https://leetcode.com/problems/string-to-integer-atoi/)

## Thought

## Code

```python
class Solution:
    def myAtoi(self, s: str) -> int:
        text = s.strip()

        if not text:
            return 0

        sign = 1
        start = 0
        word = ''

        if text[0] == '+':
            start = 1
        elif text[0] == '-':
            sign = -1
            start = 1
            
        for i in range(start, len(text)):
            if text[i].isdigit():
                word += text[i]
            else:
                break
                
        if not word:
            return 0
        
        LOW = -(2 ** 31)
        HIGH = 2 ** 31 - 1
        
        result = sign * int(word)
        if result > HIGH:
            return HIGH
        elif result < LOW:
            return LOW
        return result
```
