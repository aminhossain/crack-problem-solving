<h1 align="center"><a href="https://leetcode.com/problems/pascals-triangle/" target="_blank">Pascal's Triangle</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

Applied basic bruteforce and observations approach to solve the problem. If we follow the pattern the start and end of each row will be 1, so we can hard code this value. Now to solve the remaining position we can simply observe the value and index progression.

# Approach

<!-- Describe your approach to solving the problem. -->

#### Simple two steps to solve the problem:

- Assign each array start and end value as 1
- Now observe and do some basic math to solve the other positions

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n+m)`

# Code: JavaScript

```javascript
/**
 * @param {number} numRows
 * @return {number[][]}
 */
var generate = function (x) {
  let pascle = [];

  for (let i = 0; i < x; i++) {
    let arr = [];
    for (let j = 0; j < i + 1; j++) {
      if (j == 0 || j == i) arr.push(1);
      else arr.push(pascle[i - 1][j - 1] + pascle[i - 1][j]);
    }
    pascle.push(arr);
  }

  return pascle;
};
```

# Code: C++

```c++
class Solution {
public:
    vector<vector<int>> generate(int x) {
        vector<vector<int>> vp;

        for (int i = 0; i < x; i++) {
            vector<int> ini;
            for (int j = 0; j < i+1; j++) {
                if(j == 0 || (j-i) == 0) ini.push_back(1);
                else ini.push_back(vp[i-1][j-1]+vp[i-1][j]);
            }
            vp.push_back(ini);
        }

        return vp;
    }
};
```
