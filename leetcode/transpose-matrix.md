# Transpose Matrix Problem & Solution

Given a 2D integer array `matrix`, return the transpose of `matrix`.

The transpose of a matrix is the matrix flipped over its main diagonal, switching the matrix's row and column indices.

See the [transpose-matrix problem on LeetCode](https://leetcode.com/problems/transpose-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> transpose(vector<vector<int>>& matrix) {
    int m = matrix.size();
    int n = matrix[0].size();

    vector<vector<int>> transposed(n, vector<int>(m, 0));
    for (int i = 0; i < m; ++i) {
      for (int j = 0; j < n; ++j) {
        transposed[j][i] = matrix[i][j];
      }
    }

    return transposed;
  }
};
```
