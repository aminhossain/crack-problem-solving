<h1 align="center"><a href="https://www.codingninjas.com/studio/problems/longest-subarray-with-sum-k_6682399" target="_blank">Longest Subarray With Sum K</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

Use two pointer approach to solve the problem.

# Approach

<!-- Describe your approach to solving the problem. -->

- Init the variables left, right, sum and maxlen
- Start iterate from right pointer
- Now if sum becomes grater than K then move left pointer ahead to reduce the sum
- Otherwise if the sum equals to K take the length of the sum array `right-left+1`
- Else move the right pointer and add the value into sum
- finally return the max subarray length.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
int longestSubarrayWithSumK(vector<int> a, long long k) {
    // Write your code here
    int left = 0, right = 0, maxlen = 0;
    long long sum = a[0];

    while(right < a.size()) {
        while(left <= right && sum > k) {
            sum -= a[left];
            left++;
        }

        if(sum == k) {
            maxlen = max(maxlen, (right-left+1));
        }
        right++;

        if(right < a.size()) sum += a[right];
    }

    return maxlen;
}
```
