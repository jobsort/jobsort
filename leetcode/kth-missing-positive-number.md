# Kth Missing Positive Number Problem & Solution

See the [kth missing positive number problem on LeetCode](https://leetcode.com/problems/kth-missing-positive-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findKthPositive(vector<int>& arr, int k) {
    int i = 1, j = 0, count = 0;
    while (j < arr.size()) {
      if (arr[j] != i) {
        if (++count == k) {
          return i;
        }
      } else {
        ++j;
      }

      ++i;
    }

    return arr.back() + k - count;
  }
};
```
