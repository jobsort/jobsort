---
name: "01 Matrix"
title: "LeetCode 01 Matrix Solution"
description: "Solution for the 01 matrix problem from LeetCode."
published: "2023-03-07 PDT"
modified: "2023-03-07 PDT"
---

# 01 Matrix Problem & Solution

See the [01 matrix problem on LeetCode](https://leetcode.com/problems/01-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> updateMatrix(vector<vector<int>>& mat) {
    vector<vector<int>> dp(mat.size(), vector<int>(mat[0].size()));

    int infinity = mat.size() + mat[0].size();

    // traverses forward from top left to bottom right
    for (int i = 0; i < dp.size(); ++i) { // O(n)
      for (int j = 0; j < dp[0].size(); ++j) { // O(m)
        if (mat[i][j] == 0) { continue; }

        int top = infinity, left = infinity;
        if (i > 0) { top = dp[i - 1][j]; }
        if (j > 0) { left = dp[i][j - 1]; }

        dp[i][j] = min(top, left) + 1;
      }
    }

    // traverses backwards from bottom right to top left
    for (int i = dp.size() - 1; i >= 0; --i) { // O(n)
      for (int j = dp[0].size() - 1; j >= 0; --j) { // O(m)
        if (mat[i][j] == 0) { continue; }

        int bottom = infinity, right = infinity;
        if (i < dp.size() - 1) { bottom = dp[i + 1][j]; }
        if (j < dp[0].size() - 1) { right = dp[i][j + 1]; }

        dp[i][j] = min(dp[i][j], min(bottom, right) + 1);
      }
    }

    return dp;
  }
};
```
