<h1 align="center"><a href="https://leetcode.com/problems/reverse-pairs/" target="_blank">Reverse Pairs</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(2N*logn)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(N)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
class Solution {
public:
    int merge(vector<int>& arr, int low, int mid, int high) {
        vector<int> tmp;
        int left = low, right = mid+1;
        int cnt = 0;

        while(left <= mid && right <= high) {
            if(arr[left] <= arr[right]) {
                tmp.push_back(arr[left]);
                left++;
            } else {
                tmp.push_back(arr[right]);
                cnt += (mid-left+1);
                right++;
            }
        }

        while(left <= mid) {
            tmp.push_back(arr[left]);
            left++;
        }

        while(right <= high) {
            tmp.push_back(arr[right]);
            right++;
        }

        for (int i = low; i <= high; i++) {
            arr[i] = tmp[i-low];
        }

        return cnt;

    }

    int countPairs(vector<int>& arr, int low, int mid, int high) {
        int cnt = 0, right = mid+1;

        for (int i = low; i <= mid; i++) {
            while (right <= high && (long long)arr[i] > (long long)2*arr[right]) right++;
            cnt += (right - (mid+1));
        }

        return cnt;
    }

    int mergeSort(vector<int>& arr, int low, int high) {
        int cnt = 0;
        if(low >= high) return cnt;
        int mid = (low+high)/2;

        cnt += mergeSort(arr, low, mid);
        cnt += mergeSort(arr, mid+1, high);
        cnt += countPairs(arr, low, mid, high);
        merge(arr, low, mid, high);

        return cnt;
    }

    int reversePairs(vector<int>& nums) {
        return mergeSort(nums, 0, nums.size()-1);
    }
};
```
