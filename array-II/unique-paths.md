<h1 align="center"><a href="https://leetcode.com/problems/unique-paths/" target="_blank">Grid Unique Paths</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n+m)` for DP solution.\
  `O(n) or O(m)` for Combinatorics solution.

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n+m)` for DP solution.\
  `O(1)` for Combinatorics solution.

# Code: JavaScript

```javascript
/**
 * Combinatorics solution
 * @param {number} m
 * @param {number} n
 * @return {number}
 */

var uniquePaths = function (m, n) {
  let N = m + n - 2;
  let r = n - 1;
  let ans = 1;

  for (let i = 1; i <= r; i++) {
    ans = (ans * (N - r + i)) / i;
  }

  return ans;
};
```

# Code: C++

```c++
/**
 * DP solution
 * @param {number} m
 * @param {number} n
 * @return {number}
 */
class Solution {
public:
    int countPaths(int i, int j, int n, int m, vector<vector<int>>& dp) {
        if(i == (n-1) && j == (m-1)) return 1;
        if(i >= n || j >= m) return 0;

        if(dp[i][j] != -1) return dp[i][j];
        return dp[i][j] = countPaths(i+1, j, n, m, dp) + countPaths(i, j+1, n, m, dp);
    }

    int uniquePaths(int m, int n) {
        vector<vector<int>> dp(n+1, vector<int>(m+1, -1));
        return countPaths(0,0,n,m,dp);
    }
};
```
