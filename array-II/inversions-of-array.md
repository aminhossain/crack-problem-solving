<h1 align="center"><a href="https://leetcode.com/problems/sort-colors/" target="_blank">Sort Colors</a></h1>

# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
  <!-- Add your time complexity here, e.g. $$O(n)$$ -->

  `O(nlogn)`

- Space complexity:
  <!-- Add your space complexity here, e.g. $$O(n)$$ -->
  `O(1)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
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

int mergeSort(vector<int>& arr, int low, int high) {
    int cnt = 0;
    if(low >= high) return cnt;
    int mid = (low+high)/2;

    cnt += mergeSort(arr, low, mid);
    cnt += mergeSort(arr, mid+1, high);
    cnt += merge(arr, low, mid, high);

    return cnt;
}

int numberOfInversions(vector<int>&a, int n) {
    // Write your code here.
    int ans = mergeSort(a, 0, n-1);

    return ans;
}
```
