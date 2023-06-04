# Unique Paths II Problem & Solution

See the [unique paths ii problem on LeetCode](https://leetcode.com/problems/unique-paths-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int uniquePathsWithObstacles(vector<vector<int>>& grid) {
    vector<vector<int>> dp(grid.size(), vector<int>(grid[0].size()));
    dp[0][0] = 1;

    // O(nm)
    for (int i = 0; i < dp.size(); ++i) {
      for (int j = 0; j < dp[i].size(); ++j) {
        if (grid[i][j] == 1) {
          dp[i][j] = 0;
          continue;
        }

        if (i > 0 && grid[i - 1][j] == 0) {
          dp[i][j] += dp[i - 1][j];
        }
        if (j > 0 && grid[i][j - 1] == 0) {
          dp[i][j] += dp[i][j - 1];
        }
      }
    }

    return dp.back().back();
  }
};
```
