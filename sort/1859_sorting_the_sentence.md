# [Easy] 1859. Sorting the Sentence

## Question

[[Easy] 1859. Sorting the Sentence](https://leetcode.com/problems/sorting-the-sentence/)

## Thought

先以空格將每個 word 切開，並把數字放到單字的最前面，接著使用內建 `sort()` 排序，最後再將開頭的數字移除並回傳完整句子。

## Code

```python
class Solution:
    def sortSentence(self, s: str) -> str:
        word_list = [x[-1:] + x[:-1] for x in s.split(' ')]
        word_list.sort()
        result = [x[1:] for x in word_list]
        
        return ' '.join(result)
```
