<h1 align="center"><a href="https://leetcode.com/problems/4sum/" target="_blank">4Sum</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n^3)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(2n)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& v, int target) {
        vector<vector<int>> ans;
        sort(v.begin(), v.end());
        int n = v.size();

        for(int i = 0; i < n; i++) {
            if(i > 0 && v[i] == v[i-1]) continue;
            for(int j = i+1; j < n; j++) {
                if(j > i+1 && v[j] == v[j-1]) continue;
                int k = j+1, l = n-1;
                while(k < l) {
                    long long sum = (long long)v[i] + (long long)v[j] + (long long)v[k] + (long long)v[l];

                    if(sum < target) k++;
                    else if(sum > target) l--;
                    else {
                        ans.push_back({v[i], v[j], v[k], v[l]});
                        k++, l--;
                        while(k < l && v[k] == v[k-1]) k++;
                        while(k < l && v[l] == v[l+1]) l--;
                    }
                }
            }
        }

        return ans;
    }
};
```
