<h1 align="center"><a href="#" target="_blank">Search in a sorted 2D matrix</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(NlogN)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var sortColors = function (arr, target) {
  let r = arr.length,
    c = arr[0].length;
  let lo = 0,
    hi = r * c - 1;

  while (lo <= hi) {
    let mid = lo + (hi - lo) / 2;
    let val = arr[mid / c][mid % c];
    if (val == target) return true;
    if (val < target) lo = mid + 1;
    else hi = mid - 1;
  }

  return false;
};
```

# Code: C++

```c++
class Solution {
public:
    bool search2DArray(vector<vector<int> >& arr, int target) {
        int r = arr.size(), c = arr[0].size();
        int lo = 0, hi = (r*c)-1;

        while(lo <= hi) {
            int mid = (lo + (hi-lo)/2);
            int val = arr[mid/c][mid%c];
            if(val ==  target) return true;
            if(val < target) lo = mid + 1;
            else hi = mid - 1;
        }

        return false;
    }
};
```
