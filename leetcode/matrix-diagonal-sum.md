# Matrix Diagonal Sum Problem & Solution

See the [matrix diagonal sum problem on LeetCode](https://leetcode.com/problems/matrix-diagonal-sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int diagonalSum(vector<vector<int>>& mat) {
    int sum = 0;
    for (int i = 0; i < mat.size(); ++i) {
      sum += mat[i][i];
      if (mat.size() % 2 == 0 || i != mat.size() / 2) {
        sum += mat[i][mat[i].size() - i - 1];
      }
    }

    return sum;
  }
};
```
