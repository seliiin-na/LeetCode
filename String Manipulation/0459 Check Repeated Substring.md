[Problem Link](https://leetcode.com/problems/repeated-substring-pattern/description/)

### Things to Note:
1. only need to check up to the halfway point of s (bc else no way to form a _repeated_ substring)
2. returns `True` if there is _ANY_ substring that satisfies

```python
class Solution:
    def repeatedSubstringPattern(self, s: str) -> bool:
        candidate = ''
        
        # only need to check for 1st half, bc no way 
        # to have a *repeated* substring begining in 2nd half
        for i in range(len(s) // 2):
            candidate += s[i]

            # len(s) must be a multiple of len(candicate)
            if (len(s) % len(candidate)) == 0:

                # s contains a multiple of candidate
                # need '//' to get int type for '*'
                if candidate * (len(s)//len(candidate)) == s:
                    return True
```
