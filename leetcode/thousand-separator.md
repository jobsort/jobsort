---
name: "Thousand Separator"
title: "LeetCode Thousand Separator Solution"
description: "Solution for the thousand separator problem from LeetCode."
published: "2023-01-02 PDT"
modified: "2023-01-02 PDT"
---

# Thousand Separator Problem & Solution

See the [thousand separator problem on LeetCode](https://leetcode.com/problems/thousand-separator).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string thousandSeparator(int n) {
    string s = to_string(n);

    int i = 3;
    while (i < s.size()) {
      s.insert(s.size() - i, ".");
      i += 4;
    }
    
    return s;
  }
};
```
