<h1 align="center"><a href="https://leetcode.com/problems/missing-number/" target="_blank">Missing Number</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

We can use bitwise XoR trick to solve this problem. As we know in bitwise XoR rule when the bits are similar it results zero. So using this theory we can easily see that if we take a variable which will increase from `0 to n` and it XoR with the array values then the similar values will eleminate each other. Thus we'll get our missing number. For better understand see the code.

# Approach

<!-- Describe your approach to solving the problem. -->

- Decalre a variable called `x` // this will be the increasing variable.
- Now init the variable called `missing` with zero
- Iterate the `nums` array and XoR the `nums[i]` values with the increasing `x` // this will eleminate the nums[i]
- finally return the `missing` number.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var missingNumber = function (nums) {
  let x = 0;
  let missing = 0;

  for (let i = 0; i <= nums.length; i++) {
    if (i < nums.length) {
      missing ^= nums[i];
    }
    if (x > 0) missing ^= x;
    x++;
  }
  return missing;
};
```

# Code: C++

```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int x = 0;
        int missing = 0;

        for(int i = 0; i <= nums.size(); i++) {
            if(i < nums.size()) {
                missing ^= nums[i];
            }
            if(x > 0) missing ^= x;
            x++;
        }
        return missing ;
    }
};
```
