# Spiral Matrix Problem & Solution

See the [spiral matrix problem on LeetCode](https://leetcode.com/problems/spiral-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);cout.setstate(ios_base::failbit);return 0;}();

class Solution {
public:
  vector<int> spiralOrder(vector<vector<int>>& matrix) {
    vector<int> results;

    int m = matrix.size(), n = matrix[0].size();
    int d = 0;
    while (true) {
      if (d >= m - d) { break; }
      for (int j = d; j < n - d; ++j) {
        results.push_back(matrix[d][j]);
      }

      if (d >= n - d) { break; }
      for (int i = d + 1; i < m - d; ++i) {
        results.push_back(matrix[i][n - d - 1]);
      }

      if (d == m / 2) { break; }
      for (int j = n  - d - 2; j >= d; --j) {
        results.push_back(matrix[m - d - 1][j]);
      }

      if (d == n / 2) { break; }
      for (int i = m - d - 2; i > d; --i) {
        results.push_back(matrix[i][d]);
      }

      ++d;
    }

    return results;
  }
};
```
