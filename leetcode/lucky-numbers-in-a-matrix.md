# Lucky Numbers in a Matrix Problem & Solution

See the [lucky numbers in a matrix problem on LeetCode](https://leetcode.com/problems/lucky-numbers-in-a-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> luckyNumbers (vector<vector<int>>& matrix) {
    int m = matrix.size(), n = matrix[0].size();
    vector<int> rows(m, numeric_limits<int>::max());
    vector<int> cols(n, numeric_limits<int>::min());

    for (int i = 0; i < m; ++i) {
      for (int j = 0; j < n; ++j) {
        rows[i] = min(rows[i], matrix[i][j]);
      }
    }

    for (int j = 0; j < n; ++j) {
      for (int i = 0; i < m; ++i) {
        cols[j] = max(cols[j], matrix[i][j]);
      }
    }

    vector<int> results;
    for (int i = 0; i < m; ++i) {
      for (int j = 0; j < n; ++j) {
        if (matrix[i][j] == rows[i] &&
            matrix[i][j] == cols[j]) {
          results.push_back(matrix[i][j]);
        }
      }
    }

    return results;
  }
};
```
