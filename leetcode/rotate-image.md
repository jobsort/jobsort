---
name: "Rotate Image"
title: "LeetCode Rotate Image Solution"
description: "Solution for the rotate image problem from LeetCode."
published: "2023-03-01 PDT"
modified: "2023-03-01 PDT"
---

# Rotate Image Problem & Solution

See the [rotate image problem on LeetCode](https://leetcode.com/problems/rotate-image).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  void rotate(vector<vector<int>>& matrix) {
    reverse(matrix.begin(), matrix.end());

    for (int i = 0; i < matrix.size(); ++i) {
      for (int j = i + 1; j < matrix[i].size(); ++j) {
        swap(matrix[i][j], matrix[j][i]);
      }
    }
  }
};
```
