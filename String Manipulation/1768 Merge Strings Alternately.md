[Problem Link](https://leetcode.com/problems/merge-strings-alternately/description/?envType=study-plan-v2&envId=leetcode-75)

### Things to Note:
1. Need to find the max length of the 2 strings
2. Add one char at a time from each string (while the str still has chars left)

```py
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        # create a list to append letters
        result = []

        n = max(len(word1), len(word2))

        # while at least one word has not reached end
        for i in range(n):
            if i < len(word1):
                result += word1[i]
            if i < len(word2):
                result += word2[i]
                
        return "".join(result)

```
