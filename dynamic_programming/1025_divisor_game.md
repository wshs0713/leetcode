# [Easy] 1025. Divisor Game

## Question

[[Easy] 1025. Divisor Game](https://leetcode.com/problems/divisor-game/)

## Thought

依序列出 n 值，找規律:

- n = 1, Alice no move => Alice lose. Output is `False`.
- n = 2
  - Alice: chooses 1.
  - Bob: 0 < x < 1, no move.
  - Alice win, output is `True`.
- n = 3
  - Alice: chooses 1.
  - Bob: 0 < x < 2, Bob chooses 1.
  - Alice: 0 < x < 1, no move.
  - Alice lose, output is `False`.
- n = 4
  - Alice: chooses 1.
  - Bob: 0 < x < 3, Bob chooses 1.
  - Alice: 0 < x < 2, Alice chooses 1.
  - Bob: 0 < x < 1, no move.
  - Alice win, output is `True`.
- n = 5
  - Alice: chooses 1.
  - Bob: 0 < x < 4, Bob chooses 1.
  - Alice: 0 < x < 3, no move.
  - Bob: 0 < x < 2, Bob chooses 1.
  - Alice: 0 < x < 1, no move.
  - Alice lose, output is `False`.

可以發現當 n 為偶數時，Alice 會贏，output is `True`.

## Code

```python
class Solution:
    def divisorGame(self, n: int) -> bool:
        if n % 2 == 0:
            return True
        return False
```
