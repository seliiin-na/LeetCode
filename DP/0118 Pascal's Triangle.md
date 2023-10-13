[Problem Link](https://leetcode.com/problems/pascals-triangle/description/)

### why DP?
* optimal substructure (use info from prev row to compute the present row)
* overlapping subproblems (same 2 nums to compute a value over and over)

  
### Things to Note:
1. visualize the triangle as if it were left-aligned <img width="300" alt="image" src="https://github.com/seliiin-na/LeetCode/assets/89162258/8caddd4f-3f9e-485c-b5e9-48bf55af1327">

2. **Base case:** <br>
   the value at the beginning & end of a row is 1
3. **Recurrence case:** <br>
   each num = sum of 2 nums directly above it <br>
 ```triangle[row][col] = triangle[row-1][col-1] + triangle[row-1][col]```


```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        result = []
        # base case: at least 1 row
        result.append([1])

        # for the rest of the triangle
        for i in range(1, numRows):
            curr_row = []
            prev_row = result[i - 1]
            # edge
            curr_row.append(1)
            # use dp to accumulate sum from prev row
            for j in range(0, len(prev_row) - 1):
                curr_row.append(prev_row[j] + prev_row[j + 1])
            # edge
            curr_row.append(1)
            result.append(curr_row)

        return result
```
