---
name: "Count Asterisks"
title: "LeetCode Count Asterisks Solution"
description: "Solution for the count asterisks problem from LeetCode."
published: "2023-01-30 PDT"
modified: "2023-01-30 PDT"
---

# Count Asterisks Problem & Solution

See the [count asterisks problem on LeetCode](https://leetcode.com/problems/count-asterisks).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int countAsterisks(string s) {
    int pipes = 0, asterisks = 0, total = 0;
    for (auto c : s) {
      if (c == '|') {
        if (++pipes % 2 == 1) {
          total += asterisks;
        }

        asterisks = 0;
      } else if (c == '*') {
        ++asterisks;
      }
    }

    return total + asterisks;
  }
};
```
