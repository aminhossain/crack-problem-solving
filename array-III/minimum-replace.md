<h1 align="center"><a href="https://leetcode.com/problems/minimum-replacements-to-sort-the-array/" target="_blank">Minimum Replacements to Sort the Array
</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

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
var minimumReplacement = function (nums) {
  let size = nums.length;
  if (size == 1) return 0;

  let last = nums[size - 1];
  let cnt = 0;

  for (let i = size - 2; i >= 0; i--) {
    if (nums[i] > last) {
      let div = Math.floor(nums[i] / last);
      if (nums[i] % last) div++;
      last = Math.floor(nums[i] / div);
      cnt += div - 1;
    } else {
      last = nums[i];
    }
  }

  return cnt;
};
```

# Code: C++

```c++
class Solution {
public:
    long long minimumReplacement(vector<int>& nums) {
        int size = nums.size();
        if(size == 1) return 0;

        int last = nums[size-1];
        long long cnt = 0;

        for(int i = size-2; i >= 0; i--) {
            if(nums[i] > last) {
                int div = nums[i] / last;
                if(nums[i]%last) div++;
                last = nums[i] / div;
                cnt += (div-1);
            } else {
                last = nums[i];
            }
        }

        return cnt;
    }
};
```
