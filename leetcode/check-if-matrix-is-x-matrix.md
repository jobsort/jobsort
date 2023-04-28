# Check if Matrix is X-Matrix Problem & Solution

See the [check if matrix is x-matrix problem on LeetCode](https://leetcode.com/problems/check-if-matrix-is-x-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool checkXMatrix(vector<vector<int>>& grid) {
    for (int i = 0, ii = grid.size(), jj = grid[i].size(); i < ii; ++i) {
      for (int j = 0; j < jj; ++j) {
        if (i == j || i == ii - j - 1) {
          if (grid[i][j] == 0) {
            return false;
          }
        } else if (grid[i][j] != 0) {
          return false;
        }
      }
    }

    return true;
  }
};
```
