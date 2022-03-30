#### Things to note:
* use one-pass hash table
* find the index of the complement of the curr looping #

```cpp
vector<int> twoSum(vector<int>& nums, int target) {
      unordered_map<int, int> indices;
      for (int i = 0; i < nums.size(); i++) {
          // if find the compliment of the currernt num before the map ends, return
          if (indices.find(target - nums[i]) != indices.end()) {
              return {indices[target - nums[i]], i};
          }
          // put this num into map if can't find complement
          indices[nums[i]] = i; 
      }
      return {};
}
```
