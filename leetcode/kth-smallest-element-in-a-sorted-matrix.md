# Kth Smallest Element in a Sorted Matrix Problem & Solution

See the [kth smallest element in a sorted matrix problem on LeetCode](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int kthSmallest(vector<vector<int>>& matrix, int k) {
    multiset<int> s{less<int>()};

    for (int i = 0; i < matrix.size(); ++i) {
      for (int j = 0; j < matrix[i].size(); ++j) {
        s.insert(matrix[i][j]);
        if (s.size() > k) {
          s.erase(--s.end());
        }
      }
    }

    return *(--s.end());
  }
};
```
