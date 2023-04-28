---
name: "Fibonacci Number"
title: "LeetCode Fibonacci Number Solution"
description: "Solution for the Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1."
published: "2021-08-08 PDT"
modified: "2021-08-08 PDT"
---

# Fibonacci Number Problem & Solution

The Fibonacci numbers, commonly denoted `F(n)` form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1.
That is,

```
F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.
```

Given `n`, calculate `F(n)`.

See the [fibonacci number problem on LeetCode](https://leetcode.com/problems/fibonacci-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int fib(int n) {
    if (n == 0) {
      return 0;
    } else if (n == 1) {
      return 1;
    } else {
      int first = 0;
      int second = 1;

      for (int i = 2; i <= n; ++i) {
        int tmp = first + second;

        first = second;
        second = tmp;
      }

      return second;
    }
  }
};
```
