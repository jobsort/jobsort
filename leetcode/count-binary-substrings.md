---
name: "Count Binary Substrings"
title: "LeetCode Count Binary Substrings Solution"
description: "Solution for the count binary substrings problem from LeetCode."
published: "2022-12-05 PDT"
modified: "2022-12-05 PDT"
---

# Count Binary Substrings Problem & Solution

See the [count binary substrings problem on LeetCode](https://leetcode.com/problems/count-binary-substrings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int countBinarySubstrings(string s) {
    int result = 0;

    int count = 0;
    for (int i = 0; i < s.size(); ++i) {
      int j = i;
      while (j < s.size() && s[i] == s[j]) { ++j; }

      result += min(count, j - i);
      count = j - i;
      i = j - 1;
    }

    return result;
  }
};
```
