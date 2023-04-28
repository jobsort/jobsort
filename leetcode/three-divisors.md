---
name: "Three Divisors"
title: "LeetCode Three Divisors Solution"
description: "Solution for the three divisors problem from LeetCode."
published: "2023-04-01 PDT"
modified: "2023-04-01 PDT"
---

# Three Divisors Problem & Solution

See the [three divisors problem on LeetCode](https://leetcode.com/problems/three-divisors).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isThree(int n) {
    int count = 1;
    for (int i = 2; i <= n; ++i) {
      if (n % i == 0) {
        ++count;
      }

      // Tests for early exit.
      if (count > 3) {
        break;
      }
    }

    return count == 3;
  }
};
```
