[Problem Link](https://leetcode.com/problems/move-zeroes/solutions/562911/two-pointers-technique-python-o-n-time-o-1-space/)
### Things to Note:
1. move all non-zero element to the left
2. two pointers: <br>
   one for keeping track of where to put the next non-zero value <br>
   one for iterating thru the array

<img width="400" alt="image" src="https://github.com/seliiin-na/LeetCode/assets/89162258/c09a1e01-097a-46d2-8103-36781ff61b6f">

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        # 2 pointer approach
        left = 0
        
        # use right pointer to iterate thru the list
        for right in range(len(nums)):
            if nums[right] != 0: 
                # swap the zero & non-zero val
                nums[left], nums[right] = nums[right], nums[left]

               # update the next available slot to put the non-zero val
                left += 1 

        return nums
```
