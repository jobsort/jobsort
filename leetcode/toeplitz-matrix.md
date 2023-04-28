# Toeplitz Matrix Problem & Solution

Given an `m x n` matrix, return true if the matrix is Toeplitz.
Otherwise, return false.

A matrix is Toeplitz if every diagonal from top-left to bottom-right has the same elements.

See the [Toeplitz matrix problem on LeetCode](https://leetcode.com/problems/toeplitz-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isToeplitzMatrix(vector<vector<int>>& matrix) {
    for (int i = 1; i < matrix.size(); ++i) {
      for (int j = 1; j < matrix[i].size(); ++j) {
        if (matrix[i][j] != matrix[i - 1][j - 1]) {
          return false;
        }
      }
    }

    return true;
  }
};
```
