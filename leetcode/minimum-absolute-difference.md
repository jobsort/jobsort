---
name: "Minimum Absolute Difference"
title: "LeetCode Minimum Absolute Difference Solution"
description: "Solution for the minimum absolute difference problem from LeetCode."
published: "2022-12-17 PDT"
modified: "2022-12-17 PDT"
---

# Minimum Absolute Difference Problem & Solution

See the [minimum absolute difference problem on LeetCode](https://leetcode.com/problems/minimum-absolute-difference).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> minimumAbsDifference(vector<int>& arr) {
    sort(arr.begin(), arr.end());

    int diff = numeric_limits<int>::max();
    for (int i = 0; i < arr.size() - 1; ++i) {
      diff = min(diff, arr[i + 1] - arr[i]);
    }

    vector<vector<int>> results;
    for (int i = 0; i < arr.size() - 1; ++i) {
      if (arr[i + 1] - arr[i] == diff) {
        results.push_back({arr[i], arr[i+1]});
      }
    }

    return results;
  }
};
```
