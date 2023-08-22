<h1 align="center"><a href="https://leetcode.com/problems/merge-intervals/" target="_blank">Merge Intervals</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(n)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(nlogn+n)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {

        if(intervals.size() == 1) return intervals;

        vector<vector<int> > ans;
        int size = intervals.size();

        sort(intervals.begin(), intervals.end(), [](const vector<int>& a, const vector<int>& b) {
            return a[0] < b[0];
        });

        for(int i = 0; i < size; i++) {
            int j = i;

            while(j+1 < size && intervals[i][1] >= intervals[j+1][0]) {
                intervals[i][1] = max(intervals[j+1][1], intervals[i][1]);
                j++;
            }

            if(j >= size) j--;
            ans.push_back({intervals[i][0], intervals[i][1]});
            i = j;
        }

        return ans;
    }
};
```
