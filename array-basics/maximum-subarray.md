<h1 align="center"><a href="https://leetcode.com/problems/maximum-subarray/" target="_blank">Maximum Subarray</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

The intuition of the algorithm is not to consider the subarray as a part of the answer if its sum is less than 0. A subarray with a sum less than 0 will always reduce our answer and so this type of subarray cannot be a part of the subarray with maximum sum.

Here, we will iterate the given array with a single loop and while iterating we will add the elements in a sum variable. Now, if at any point the sum becomes less than 0, we will set the sum as 0 as we are not going to consider any subarray with a negative sum. Among all the sums calculated, we will consider the maximum one.

Thus we can solve this problem with a single loop.

# Approach

- Declare variables called `max_so_far` and `max_end` and initialize the variables with first element of the array
- Iterate the array from index 1 to n-1
- Update the `max_end` and `max_so_far` by progress of the array
- finally return the `max_so_far`
<!-- Describe your approach to solving the problem. -->

#### Simple two steps to solve the problem:

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
var maxSubArray = function (nums) {
  let max_so_far = nums[0];
  let max_end = nums[0];

  for (let i = 1; i < nums.length; i++) {
    max_end = Math.max(nums[i], max_end + nums[i]);
    max_so_far = Math.max(max_so_far, max_end);
  }

  // console.log(max_so_far)
  return max_so_far;
};
```

# Code: C++

```c++
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int max_so_far = nums[0];
        int max_end = nums[0];

        for(int i = 1; i < nums.size(); i++) {
            max_end = max(nums[i], max_end+nums[i]);
            max_so_far = max(max_so_far, max_end);
        }

        return max_so_far;
    }
};
```
