---
name: "Combinations"
title: "LeetCode Combinations Solution"
description: "Solution for the combinations problem from LeetCode."
published: "2023-01-01 PDT"
modified: "2023-01-01 PDT"
---

# Combinations Problem & Solution

See the [combinations problem on LeetCode](https://leetcode.com/problems/combinations).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC optimization("max-inline-insns-recursive-auto")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> combine(int n, int k) {
    vector<vector<int>> results;
    vector<int> result;

    combine(n, k, result, results);

    return results;
  }

private:
  void combine(int n, int k, vector<int>& result, vector<vector<int>>& results) {
    if (result.size() == k) {
      results.push_back(result);
      return;
    }

    int j = result.size() > 0 ? result.back() + 1 : 1;
    for (int i = j; i <= n; ++i) {
      result.push_back(i);
      combine(n, k, result, results);
      result.pop_back();
    }
  }
};
```
