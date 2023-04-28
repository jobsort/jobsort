---
name: "Search a 2D Matrix"
title: "LeetCode Search a 2D Matrix Solution"
description: "Solution for the search a 2d matrix problem from LeetCode."
published: "2023-01-27 PDT"
modified: "2023-01-27 PDT"
---

# Search a 2D Matrix Problem & Solution

See the [search a 2d matrix problem on LeetCode](https://leetcode.com/problems/search-a-2d-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool searchMatrix(vector<vector<int>>& matrix, int target) {
    int low = 0, high = matrix.size() - 1;
    while (low <= high) {
      int mid = low + (high - low) / 2;

      auto vect = matrix[mid];
      auto it = upper_bound(vect.begin(), vect.end(), target);

      if (it != vect.begin() && *prev(it) == target) {
        return true;
      }

      if (it == vect.begin()) {
        high = mid - 1;
      } else {
        low = mid + 1;
      }
    }

    return false;
  }
};
```
