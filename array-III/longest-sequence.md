<h1 align="center"><a href="https://leetcode.com/problems/longest-consecutive-sequence/" target="_blank">Longest Consecutive Sequence
</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

We will declare 2 variables,

- `cnt` → (to store the length of the current sequence),
- `longest` → (to store the maximum length).
- Then,
  - First, we will put all the array elements into the set data structure.
  - For every element, x, that can be a starting number(i.e. x-1 does not exist in the set) we will do the following:
  - We will set the length of the current sequence(cnt) to 1.
  - Then, again using the set, we will search for the consecutive elements such as x+1, x+2, and so on, and find the maximum possible length of the current sequence. This length will be stored in the variable ‘cnt’.
  - After that, we will compare ‘cnt’ and ‘longest’ and update the variable ‘longest’ with the maximum value (i.e. longest = max(longest, cnt)).
  - Finally, we will have the answer i.e. ‘longest’.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)~O(2N)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(N)`

# Code: JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var longestConsecutive = function (nums) {
  if (nums.length == 0) return 0;
  let st = new Set();
  let longest = 1;

  for (let i = 0; i < nums.length; i++) {
    st.add(nums[i]);
  }

  for (let i = 0; i < nums.length; i++) {
    if (!st.has(nums[i] - 1)) {
      let cnt = 1;
      let x = nums[i];

      while (st.has(x + 1)) {
        x += 1;
        cnt += 1;
      }

      longest = Math.max(longest, cnt);
    }
  }

  return longest;
};
```

# Code: C++

```c++
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {

        if(nums.size() == 0) return 0;

        int longest = 1;
        unordered_set<int> st;

        for (int i = 0; i < nums.size(); i++) {
            st.insert(nums[i]);
        }

        for(auto it : st) {
            if(st.find(it-1) == st.end()) {
                int cnt = 1;
                int x = it;

                while(st.find(x+1) != st.end()) {
                    x++;
                    cnt++;
                }

                longest = max(longest, cnt);
            }
        }

        return longest;
    }
};
```
