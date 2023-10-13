[Problem Link](https://leetcode.com/problems/first-missing-positive/description/) <br>
[NeetCode Explanation](https://www.google.com/search?q=leetcode+find+first+missing+positive&oq=leetcode+find+first+&gs_lcrp=EgZjaHJvbWUqBwgAEAAYgAQyBwgAEAAYgAQyBwgBEAAYgAQyBggCEEUYOTIHCAMQABiABDIKCAQQABiGAxiKBTIKCAUQABiGAxiKBTIKCAYQABiGAxiKBTIKCAcQABiGAxiKBdIBCDM5NDFqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8#fpstate=ive&vld=cid:247c56e0,vid:8g78yfzMlao,st:0)

**Need further modification + understanding!!
### Things to Note:
1. No matter what input values we get, n belongs to the set `{1, len(input_arr) + 1}`
2. scan input, replace all negative w/ 0's (bc neg. don't matter)
3. 
4. use `HashSet` to store all the existing nums
5.  then starting from 1 (smallest positive integer), check if it is in the set. 


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

