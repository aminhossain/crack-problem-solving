<h1 align="center"><a href="https://leetcode.com/problems/two-sum/" target="_blank">Two Sum</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

- We will select the element of the array one by one using a loop(say i).
- Then we will check if the other required element(i.e. target-nums[i]) exists in the hashMap.
  - If that element exists, then we will return “YES” for the first variant or we will return the current index i.e. i, and the index of the element found using map i.e. mp[target-nums[i]].
  - If that element does not exist, then we will just store the current element in the hashMap along with its index. Because in the future, the current element might be a part of our answer.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n)`

# Code: JavaScript

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  let obj = new Map();
  for (let i = 0; i < nums.length; i++) {
    let need = target - nums[i];
    if (obj.has(need)) {
      return [obj.get(need), i];
    }
    obj.set(nums[i], i);
  }

  return [];
};
```

# Code: C++

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> ump;

        for(int i = 0; i < nums.size(); i++) {
            int need = target - nums[i];
            if(ump.find(need) != ump.end()) {
                return {ump[need], i};
            }
            ump[nums[i]] = i;
        }

        return {};
    }
};
```
