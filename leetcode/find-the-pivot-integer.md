---
name: "Find the Pivot Integer"
title: "LeetCode Find the Pivot Integer Solution"
description: "Solution for the find the pivot integer problem from LeetCode."
published: "2022-11-27 PDT"
modified: "2022-11-27 PDT"
---

# Find the Pivot Integer Problem & Solution

See the [find the pivot integer problem on LeetCode](https://leetcode.com/problems/find-the-pivot-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int pivotInteger(int n) {
    int total = n * (n + 1) / 2;
    for (int i = 1; i <= n; ++i) {
      int left = i * (i + 1) / 2;
      int right = total - left + i;
      
      if (left == right) {
        return i;
      }
    }

    return -1;
  }
};
```
