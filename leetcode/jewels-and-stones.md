---
name: "Jewels and Stones"
title: "LeetCode Jewels and Stones Solution"
description: "Solution for the jewels and stones problem from LeetCode."
published: "2023-03-03 PDT"
modified: "2023-03-03 PDT"
---

# Jewels and Stones Problem & Solution

See the [jewels and stones problem on LeetCode](https://leetcode.com/problems/jewels-and-stones).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numJewelsInStones(string jewels, string stones) {
    unordered_set<char> s{jewels.begin(), jewels.end()};

    int result = 0;
    for (char c : stones) {
      if (s.find(c) != s.end()) {
        ++result;
      }
    }

    return result;
  }
};
```
