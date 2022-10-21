Q: Find the max distance between 2 occurrances of the same number in a given array.

### Things to Note:
* use a `HashMap`: map each number to the index location of its first occurrence

```java
import java.util.*;

class Solution {
    int solution(int[] A) {
        // find the farthest distance between the same number in the array

        // use a map from number to its current index location
        HashMap<Integer, Integer> map = new HashMap<>();
        int result = 0;

        // loop through array and put distinct elements in the map
        // if inserting a new element, record its index in the array
        for (int i = 0 ; i < A.length; i++) {
            if (! map.containsKey(A[i])) {
                map.put(A[i], i);
            } else {
                // the number was already inserted, so compute the distance
                // between its current index and the index it the same num first appeared
                // update the result (compare current result and the new distance)
                result = Math.max(result, i - map.get(A[i]));
            }
        }
        return result;
    }
```
