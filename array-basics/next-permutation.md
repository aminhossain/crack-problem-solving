<h1 align="center"><a href="https://leetcode.com/problems/next-permutation/" target="_blank">Next Permutation</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

#### Simple two steps to solve the problem:

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int idx = -1, sz = nums.size();
        for (int i = sz-2; i >= 0; i--) {
            if(nums[i] < nums[i+1]) {
                idx = i; break;
            }
        }

        if(idx == -1) {
            sort(nums.begin(), nums.end());
            return;
        }

        for(int i = sz-1; i >= 0; i--) {
            if(nums[i] > nums[idx]) {
                swap(nums[i], nums[idx]); break;
            }
        }

        sort(nums.begin()+idx+1, nums.end());
    }
};
```
