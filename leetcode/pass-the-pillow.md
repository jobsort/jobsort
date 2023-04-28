---
name: "Pass the Pillow"
title: "LeetCode Pass the Pillow Solution"
description: "Solution for the pass the pillow problem from LeetCode."
published: "2023-03-26 PDT"
modified: "2023-03-26 PDT"
---

# Pass the Pillow Problem & Solution

See the [pass the pillow problem on LeetCode](https://leetcode.com/problems/pass-the-pillow).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int passThePillow(int n, int time) {
    int quotient = time / (n - 1);
    int remainder = time % (n - 1);

    return quotient % 2 == 0
      ? remainder + 1
      : n - remainder;
  }
};
```
