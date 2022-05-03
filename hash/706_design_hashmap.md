# [Easy] 706. Design HashMap

## Question

[[Easy] 706. Design HashMap](https://leetcode.com/problems/design-hashmap/)

## Thought

## Code

```python
class MyHashMap:

    def __init__(self):
        self.mapping = {}

    def put(self, key: int, value: int) -> None:
        self.mapping[key] = value

    def get(self, key: int) -> int:
        return self.mapping[key] if key in self.mapping else -1

    def remove(self, key: int) -> None:
        if key in self.mapping:
            del self.mapping[key]


# Your MyHashMap object will be instantiated and called as such:
# obj = MyHashMap()
# obj.put(key,value)
# param_2 = obj.get(key)
# obj.remove(key)
```
