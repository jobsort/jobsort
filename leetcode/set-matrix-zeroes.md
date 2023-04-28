# Set Matrix Zeroes Problem & Solution

See the [set matrix zeroes problem on LeetCode](https://leetcode.com/problems/set-matrix-zeroes).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);cout.setstate(ios_base::failbit);return 0;}();

class Solution {
public:
  void setZeroes(vector<vector<int>>& matrix) {
    bool col = false;

    for (int i = 0; i < matrix.size(); ++i) {
      if (matrix[i][0] == 0) {
        col = true;
      }

      for (int j = 1; j < matrix[i].size(); ++j) {
        if (matrix[i][j] == 0) {
          matrix[i][0] = 0;
          matrix[0][j] = 0;
        }
      }
    }

    for (int i = 1; i < matrix.size(); ++i) {
      for (int j = 1; j < matrix[i].size(); ++j) {
        if (matrix[i][0] == 0 || matrix[0][j] == 0) {
          matrix[i][j] = 0;
        }
      }
    }

    if (matrix[0][0] == 0) {
      for (int j = 0; j < matrix[0].size(); ++j) {
        matrix[0][j] = 0;
      }
    }

    if (col) {
      for (int i = 0; i < matrix.size(); ++i) {
        matrix[i][0] = 0;
      }
    }
  }
};
```
