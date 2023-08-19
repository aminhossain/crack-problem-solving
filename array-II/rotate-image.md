<h1 align="center"><a href="https://leetcode.com/problems/rotate-image/" target="_blank">Rotate Image</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

If we observe, we can see that the first column of the original matrix is the reverse of the first row of the rotated matrix, so that’s why we transpose the matrix and then reverse each row, and since we are making changes in the matrix itself space complexity gets reduced to O(1).

# Approach

<!-- Describe your approach to solving the problem. -->

- Transpose the matrix. (transposing means changing columns to rows and rows to columns)
- Reverse each row of the matrix.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O((n*n)+(n*n))`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript
/**
 * @param {number[][]} matrix
 * @return {void} Do not return anything, modify matrix in-place instead.
 */
var rotate = function (matrix) {
  let r = matrix.length;

  for (let i = 0; i < r; i++) {
    for (let j = 0; j < i; j++) {
      [matrix[i][j], matrix[j][i]] = [matrix[j][i], matrix[i][j]];
    }
  }

  for (let i = 0; i < r; i++) {
    matrix[i].reverse();
  }
};
```

# Code: C++

```c++
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int r = matrix.size();

        for (int i = 0; i < r; i++) {
            for (int j = 0; j < i; j++) {
                swap(matrix[i][j], matrix[j][i]);
            }
        }

        for(int i = 0; i < r; i++) {
            reverse(matrix[i].begin(), matrix[i].end());
        }
    }
};
```
