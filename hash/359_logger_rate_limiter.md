# [Easy] 359. Logger Rate Limiter

## Question

[[Easy] 359. Logger Rate Limiter](https://leetcode.com/problems/logger-rate-limiter/)

## Thought

## Code

```python
class Logger:

    def __init__(self):
        self.logger = {}

    def shouldPrintMessage(self, timestamp: int, message: str) -> bool:
        if message:
            if message in self.logger:
                diff = timestamp - self.logger[message]
                if diff >= 10:
                    self.logger[message] = timestamp
                    return True
                return False
            
            self.logger[message] = timestamp
            return True
        return None


# Your Logger object will be instantiated and called as such:
# obj = Logger()
# param_1 = obj.shouldPrintMessage(timestamp,message)
```
