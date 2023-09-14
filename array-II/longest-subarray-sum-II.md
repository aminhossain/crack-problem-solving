<h1 align="center"><a href="https://www.codingninjas.com/studio/problems/longest-subarray-with-sum-k_5713505" target="_blank">Longest Subarray With Sum K. (Positive +Negative)</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

We can store the prefix sum method to solve this version of the problem.

# Approach

<!-- Describe your approach to solving the problem. -->

- Init the map to keep the prefix sum with based on index.
- Start iterating the loop
- Now if sum is equal to k then we store the length of the subarray.
- Otherwise we will look for difference of `sum - k`, so that we can find the new length of the subarray whos sum is equal to k.
- finally return the max subarray length.

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(nlogn)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(n)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
#include <bits/stdc++.h>
int getLongestSubarray(vector<int>& a, int k){
    // Write your code here
    map<long long, int> preSum;
    long long sum = 0;
    int maxlen = 0;

    for(int i = 0; i < a.size(); i++) {
        sum += a[i];
        if(sum == k) {
            maxlen = max(maxlen, i+1);
        }

        long long rem = sum - k;
        if(preSum.find(rem) != preSum.end()) {
            int len = i - preSum[rem];
            maxlen = max(maxlen, len);
        }

        if (preSum.find(sum) == preSum.end()) {
            preSum[sum] = i;
        }
    }

    return maxlen;
}
```
