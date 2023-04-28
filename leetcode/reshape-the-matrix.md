# Reshape the Matrix Problem & Solution

In MATLAB, there is a handy function called reshape which can reshape an m x n matrix into a new one with a different size `r` x `c` keeping its original data.

You are given an m x n matrix `mat` and two integers `r` and `c` representing the number of rows and the number of columns of the wanted reshaped matrix.

The reshaped matrix should be filled with all the elements of the original matrix in the same row-traversing order as they were.

If the reshape operation with given parameters is possible and legal, output the new reshaped matrix; otherwise, output the original matrix.

See the [reshape the matrix problem on LeetCode](https://leetcode.com/problems/reshape-the-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
    if (mat.size() * mat[0].size() != r * c) {
      return mat;
    }

    int ii = 0;
    int jj = 0;
    vector<vector<int>> reshaped(r, vector<int>(c));
    for (int i = 0; i < reshaped.size(); ++i) {
      for (int j = 0; j < reshaped[i].size(); ++j) {
        reshaped[i][j] = mat[ii][jj];

        if (++jj == mat[ii].size()) {
          jj = 0;

          ++ii;
        }
      }
    }

    return reshaped;
  }
};
```
