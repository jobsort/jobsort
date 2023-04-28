---
name: "Valid Boomerang"
title: "LeetCode Valid Boomerang Solution"
description: "Solution for the valid boomerang problem from LeetCode."
published: "2022-12-07 PDT"
modified: "2022-12-07 PDT"
---

# Valid Boomerang Problem & Solution

See the [valid boomerang problem on LeetCode](https://leetcode.com/problems/valid-boomerang).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isBoomerang(vector<vector<int>>& points) {
    if ((points[0][0] == points[1][0] && points[0][1] == points[1][1]) ||
        (points[1][0] == points[2][0] && points[1][1] == points[2][1]) ||
        (points[0][0] == points[2][0] && points[0][1] == points[2][1])) {
      return false;
    }

    if (points[1][0] == points[0][0]) {
      return points[2][0] != points[0][0];
    }

    if (points[1][1] == points[0][1]) {
      return points[2][1] != points[0][1];
    }

    // (x3 - x1) / (x2 - x1) == (y3 - y1) / (y2 - y1)
    return ((float)points[2][0] - points[0][0]) / (points[1][0] - points[0][0]) != ((float)points[2][1] - points[0][1]) / (points[1][1] - points[0][1]);
  }
};
```
