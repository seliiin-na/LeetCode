[Problem Link](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/description/?envType=study-plan-v2&envId=leetcode-75)

### Things to Note:
1. Find the current max num of candies kids are holding
2. Return value is an array of true/false

```py
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:

        result = []
        # find the current max number of candies
        max_candies = max(candies)
        
        # compare each kid's max candy amount with rest of 
        # group
        for i in range(len(candies)):
            result.append(candies[i] + extraCandies >= max_candies)

        return result
```
