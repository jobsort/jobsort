---
name: "Can Make Arithmetic Progression from Sequence"
title: "LeetCode Can Make Arithmetic Progression from Sequence Solution"
description: "Solution for the can make arithmetic progression from sequence problem from LeetCode."
published: "2023-03-29 PDT"
modified: "2023-03-29 PDT"
---

# Can Make Arithmetic Progression from Sequence Problem & Solution

See the [can make arithmetic progression from sequence problem on LeetCode](https://leetcode.com/problems/can-make-arithmetic-progression-from-sequence).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool canMakeArithmeticProgression(vector<int>& arr) {
    sort(arr.begin(), arr.end());

    int diff = arr[1] - arr[0];
    for (int i = 1; i < arr.size() - 1; ++i) {
      if (arr[i + 1] - arr[i] != diff) {
        return false;
      }
    }

    return true;
  }
};
```
