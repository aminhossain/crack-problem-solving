<h1 align="center"><a href="https://takeuforward.org/interviews/strivers-sde-sheet-top-coding-interview-problems" target="_blank">Set Matrix Zeros</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

Applied mathematical observations to solve the problem. If we observe the pattern of pascal triangle, it's clear that every nth-row has n element in pascle triangle. Now to calculate the values of each column we can apply nCr formula here. Another hack is the first value of the column will be 1.

# Approach

<!-- Describe your approach to solving the problem. -->

#### Simple two steps to solve the problem:

- First, we will consider n as n and c as r.
- After that, we will simply calculate the value of the combination using a loop.
- The loop will run from 1 to less than r. And in each iteration, we will multiply (n-i) with the result and divide the result by (i).

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n)`

# Code: JavaScript

```javascript
/**
 * @param {number} rowIndex
 * @return {number[]}
 */
var getRow = function (rowIndex) {
  let row = [1];
  let ans = 1;
  rowIndex += 1;

  for (let i = 1; i < rowIndex; i++) {
    ans = ans * (rowIndex - i);
    ans = ans / i;

    row.push(ans);
  }

  return row;
};
```

# Code: C++

```c++
class Solution {
public:
    using ll = long long;

    vector<int> getRow(int n) {
        vector<int> row;

        ll ans = 1; n += 1;
        row.push_back(ans);

        for (ll i = 1; i < n; i++) {
            ans = ans * (n-i);
            ans = ans / i;
            row.push_back(ans);
        }
        return row;
    }
};
```
