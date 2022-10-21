Given an unsorted integer array `nums`, return the smallest missing positive integer.
You must implement an algorithm that runs in O(n) time and uses constant extra space.

### Things to Note:
* use `HashSet` to store all the existing nums
* then starting from 1 (smallest positive integer), check if it is in the set. 


```java
class Solution {
    public int firstMissingPositive(int[] nums) {
        HashSet <Integer> numbers = new HashSet<>();
        // add existing numbers to a hashset
        for (int num : nums) {
            numbers.add(num);
        }
        // starting from the smallest pos integer, check if it is in the set
        // if not, great, we just return that number
        // otherwise, add 
        for (int i = 1; i <= nums.length; i++) {
            if (! numbers.contains(i))
                return i;
        }
        // i.e. if array is [1,2,3,4], we have to return 5
        return nums.length + 1;
    }
}
```

