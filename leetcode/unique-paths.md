# Unique Paths Problem & Solution

See the [unique paths problem on LeetCode](https://leetcode.com/problems/unique-paths).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int uniquePaths(int m, int n) {
    vector<vector<int>> dp(m, vector<int>(n));
    dp[0][0] = 1;

    for (int i = 0; i < dp.size(); ++i) {
      for (int j = 0; j < dp[i].size(); ++j) {
        if (i > 0) {
          dp[i][j] += dp[i - 1][j];
        }

        if (j > 0) {
          dp[i][j] += dp[i][j - 1];
        }
      }
    }

    return dp.back().back();
  }
};
```
