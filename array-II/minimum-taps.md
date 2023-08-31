<h1 align="center"><a href="https://leetcode.com/problems/minimum-number-of-taps-to-open-to-water-a-garden/" target="_blank">Minimum Number of Taps to Open to Water a Garden</a></h1>

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
 * @param {number} n
 * @param {number[]} ranges
 * @return {number}
 */
var minTaps = function (n, ranges) {
  let mini = 0,
    maxi = 0,
    cnt = 0;

  while (maxi < n) {
    for (let i = 0; i < ranges.length; i++) {
      if (i - ranges[i] <= mini && i + ranges[i] >= maxi) {
        maxi = i + ranges[i];
      }
    }

    if (maxi == mini) return -1;
    cnt++, (mini = maxi);
  }

  return cnt;
};
```

# Code: C++

```c++
class Solution {
public:
    int minTaps(int n, vector<int>& ranges) {
        int mini = 0, maxi = 0, cnt = 0;

        while(maxi < n) {
            for(int i = 0; i < ranges.size(); i++) {
                if((i-ranges[i]) <= mini && (i+ranges[i]) >= maxi) {
                    maxi = i+ ranges[i];
                }
            }

            if(maxi == mini) return -1;
            cnt++, mini = maxi;
        }

        return cnt;
    }
};
```
