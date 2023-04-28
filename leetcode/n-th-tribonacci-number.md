---
name: "N-th Tribonacci Number"
title: "LeetCode N-th Tribonacci Number Solution"
description: "Solution for the Tribonacci sequence Tn is defined as follows: T0 = 0, T1 = 1, T2 = 1, and Tn+3 = Tn + Tn+1 + Tn+2 for n >= 0. Given n, return the value of Tn."
published: "2021-12-27 PDT"
modified: "2021-12-27 PDT"
---

# N-th Tribonacci Number Problem & Solution

The Tribonacci sequence `Tn` is defined as follows:

`T0 = 0`, `T1 = 1`, `T2 = 1`, and `Tn+3 = Tn + Tn+1 + Tn+2` for `n >= 0`.

Given `n`, return the value of `Tn`.

See the [n-th tribonacci number problem on LeetCode](https://leetcode.com/problems/n-th-tribonacci-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int tribonacci(int n) {
    int t0 = 0;
    int t1 = 1;
    int t2 = 1;

    if (n == 0) { return t0; }
    if (n == 1) { return t1; }
    if (n == 2) { return t2; }

    for (int i = 3; i <= n; ++i) {
      int t3 = t2 + t1 + t0;
      t0 = t1;
      t1 = t2;
      t2 = t3;
    }

    return t2;
  }
};
```
