---
name: "Minimum Cuts to Divide a Circle"
title: "LeetCode Minimum Cuts to Divide a Circle Solution"
description: "Solution for the minimum cuts to divide a circle problem from LeetCode."
published: "2022-11-28 PDT"
modified: "2022-11-28 PDT"
---

# Minimum Cuts to Divide a Circle Problem & Solution

See the [minimum cuts to divide a circle problem on LeetCode](https://leetcode.com/problems/minimum-cuts-to-divide-a-circle).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numberOfCuts(int n) {
    if (n == 1) { return 0; }

    return n % 2 == 0 ? n / 2 : n;
  }
};
```
