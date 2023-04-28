---
name: "Longest Common Prefix"
title: "LeetCode Longest Common Prefix Solution"
description: "Solution for the longest common prefix problem from LeetCode."
published: "2021-05-22 PDT"
modified: "2021-06-12 PDT"
---

# Longest Common Prefix Problem & Solution

Write a function to find the longest common prefix string amongst an array of strings. If there is no common prefix, return an empty string "".

See the [longest common prefix problem on LeetCode](https://leetcode.com/problems/longest-common-prefix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string longestCommonPrefix(vector<string>& strs) {
    if (strs.size() == 1) {
      return strs[0];
    }

    int max = 0;
    while (true) {
      bool ok = true;
      for (int i = 1; i < strs.size(); ++i) {
        if (max >= strs[i].size() ||
            strs[i][max] != strs[0][max]) {
          ok = false;
          break;
        }
      }

      if (ok) {
        ++max;
      } else {
        break;
      }
    }

    return strs[0].substr(0, max);
  }
};
```
