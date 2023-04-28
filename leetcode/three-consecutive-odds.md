---
name: "Three Consecutive Odds"
title: "LeetCode Three Consecutive Odds Solution"
description: "Solution for the three consecutive odds problem from LeetCode."
published: "2023-01-04 PDT"
modified: "2023-01-04 PDT"
---

# Three Consecutive Odds Problem & Solution

See the [three consecutive odds problem on LeetCode](https://leetcode.com/problems/three-consecutive-odds).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool threeConsecutiveOdds(vector<int>& arr) {
    int count = 0;
    for (int i = 0; i < arr.size(); ++i) {
      count += arr[i] % 2;

      if (i >= 3) {
        count -= arr[i - 3] % 2;
      }

      if (count == 3) {
        return true;
      }
    }

    return false;
  }
};
```
