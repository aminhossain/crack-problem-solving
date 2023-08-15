<h1 align="center"><a href="https://leetcode.com/problems/set-matrix-zeroes/" target="_blank">Set Matrix Zeros</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

The idea is, if we find any matix emelemnt 0 we'll store the row and column index of that element as pair into an array. Then we traverse the array of pairs and mark the corresponding row and column value as 0.

# Approach

<!-- Describe your approach to solving the problem. -->

#### Simple two steps to solve the problem:

- Traverse the matrix and store the row and column index as pair into an array.
- Traverse the array of pairs and mark the corresponding row and column index value as 0.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O((n*m)+(n*m)*(n+m))`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n*m)`

# Code: JavaScript

```javascript
/**
 * @param {number[][]} matrix
 * @return {void} Do not return anything, modify matrix in-place instead.
 */
var setZeroes = function (mat) {
  let row = mat.length;
  let col = mat[0].length;

  // declare the pair array
  let pair = [];

  // storing the row and col as pair
  for (let i = 0; i < row; i++) {
    for (let j = 0; j < col; j++) {
      if (mat[i][j] == 0) pair.push([i, j]);
    }
  }

  // traverse and mark the row and col values as 0
  for (let i = 0; i < pair.length; i++) {
    for (let j = 0; j < col; j++) mat[pair[i][0]][j] = 0;
    for (let j = 0; j < row; j++) mat[j][pair[i][1]] = 0;
  }
};
```

# Code: C++

```c++
class Solution {
public:
    void setZeroes(vector<vector<int>>& mat) {
        int row = mat.size();
        int col = mat[0].size();

        //declare pair
        vector<pair<int, int>> vpi;

        // storing the row and col index as pair
        for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++) {
                if(mat[i][j] == 0) vpi.push_back(make_pair(i, j));
            }
        }

        // traverse and mark the row and col index values as 0
        for(auto vp : vpi) {
            for(int i = 0; i < col; i++) mat[vp.first][i] = 0;
            for(int i = 0; i < row; i++) mat[i][vp.second] = 0;
        }
    }
};
```
