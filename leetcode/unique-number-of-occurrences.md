---
name: "Unique Number of Occurrences"
title: "LeetCode Unique Number of Occurrences Solution"
description: "Solution for the unique number of occurrences problem from LeetCode."
published: "2022-12-20 PDT"
modified: "2022-12-20 PDT"
---

# Unique Number of Occurrences Problem & Solution

See the [unique number of occurrences problem on LeetCode](https://leetcode.com/problems/unique-number-of-occurrences).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool uniqueOccurrences(vector<int>& arr) {
    unordered_map<int, int> freq;
    for (auto v : arr) {
      ++freq[v];
    }

    unordered_set<int> unique;
    for (auto [k, v] : freq) {
      unique.insert(v);
    }

    return freq.size() == unique.size();
  }
};
```
