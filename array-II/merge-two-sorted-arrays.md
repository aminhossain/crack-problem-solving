<h1 align="center"><a href="https://www.codingninjas.com/studio/problems/merge-two-sorted-arrays-without-extra-space_6898839" target="_blank">Merge Two Sorted Arrays Without Extra Space</a></h1>

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
  `O(1)`

# Code: JavaScript

```javascript

```

# Code: C++

```c++
#include<vector>

void mergeTwoSortedArraysWithoutExtraSpace(vector<long long> &a, vector<long long> &b){
	// Write your code here.
	int i = a.size()-1, j = 0;

    while(i >= 0 && j < b.size()) {
        if(j >= b.size()) break;

        if(a[i] > b[j]) {
            swap(a[i], b[j]);
            i--, j++;
        } else {
            break;
        }
    }

    sort(a.begin(), a.end());
    sort(b.begin(), b.end());
}
```
