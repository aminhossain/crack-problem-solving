<h1 align="center"><a href="https://leetcode.com/problems/powx-n/" target="_blank">Pow(x, n)</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

To solve this problem we can use Binary Exponentiation.

# Approach

<!-- Describe your approach to solving the problem. -->

- Store `n` into a temporary variable `nx`
- Check if `nx` is a negative number, in that case, make it a positive number.
- Keep on iterating until `nx` is greater than zero
- Now if `nx` is an odd power then multiply `x` with ans and reduce `nx` by 1.
- Else multiply `x` with itself and divide `nx by 2`.
- Now after the entire binary exponentiation is complete and `nx` becomes zero.
- Check if `n` is a negative value we know the answer will be `divided by 1 at the end`.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(logN)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript
/**
 * @param {number} x
 * @param {number} n
 * @return {number}
 */
var myPow = function (x, n) {
  let ans = 1.0;
  let nx = n;

  if (nx < 0) nx = -1 * nx;

  while (nx) {
    if (nx % 2) {
      ans = ans * x;
      nx -= 1;
    } else {
      x *= x;
      nx /= 2;
    }
  }

  if (n < 0) ans = 1.0 / ans;

  return ans;
};
```

# Code: C++

```c++
class Solution {
public:
    double bExpo(double x, double n) {
        double ans = 1.0;
        long long nx = n;

        if(nx < 0) nx = -1 * nx;

        while(nx) {
            if(nx % 2) {
                ans = ans * x;
                nx -= 1;
            } else {
                x *= x;
                nx /= 2;
            }
        }

        if(n < 0) ans = (double) 1.0 / (double) ans;

        return ans;
    }

    double myPow(double x, int n) {
        return bExpo(x, n);
    }
};
```
