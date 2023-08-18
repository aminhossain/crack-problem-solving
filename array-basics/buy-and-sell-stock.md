<h1 align="center"><a href="https://leetcode.com/problems/best-time-to-buy-and-sell-stock/" target="_blank">Best Time to Buy and Sell Stock</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

We will linearly travel the array. We can maintain a minimum from the start of the array and compare it with every element of the array, if it is greater than the minimum then take the difference and maintain it in max, otherwise update the minimum.

# Approach

<!-- Describe your approach to solving the problem. -->

- Create variables called minPrice and profit
- Iterate the loop from 0 to n.
- Update the minPrice if it is greater than the current minPrice element of the array
- Take the difference of the minPrice with the current element of the array and compare and maintain it in profit.
- Return the profit.

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
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function (prices) {
  let profit = 0,
    minPrice = prices[0];

  for (let i = 1; i < prices.length; i++) {
    if (prices[i] > minPrice) {
      if (prices[i] - minPrice > profit) {
        profit = prices[i] - minPrice;
      }
    } else if (prices[i] < minPrice) {
      minPrice = prices[i];
    }
  }

  return profit;
};
```

# Code: C++

```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
         int profit = 0, minPrice = prices[0];

        for(int i = 1; i < prices.size(); i++) {
            if(prices[i] > minPrice) {
                if((prices[i] - minPrice) > profit) {
                    profit = prices[i] - minPrice;
                }
            } else if(prices[i] < minPrice) {
                minPrice = prices[i];
            }
        }

        return profit;
    }
};
```
