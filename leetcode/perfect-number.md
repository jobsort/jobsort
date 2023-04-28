---
name: "Perfect Number"
title: "LeetCode Perfect Number Solution"
description: "Solution for a perfect number is a positive integer that is equal to the sum of its positive divisors, excluding the number itself. A divisor of an integer x is an integer that can divide x evenly. Given an integer n, return true if n is a perfect number, otherwise return false."
published: "2021-08-08 PDT"
modified: "2021-08-08 PDT"
---

# Perfect Number Problem & Solution

A perfect number is a positive integer that is equal to the sum of its positive divisors, excluding the number itself.
A divisor of an integer `x` is an integer that can divide `x` evenly.

Given an integer `n`, return true if `n` is a perfect number, otherwise return false.

See the [perfect number problem on LeetCode](https://leetcode.com/problems/perfect-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool checkPerfectNumber(int num) {
    if (num == 1) {
      return false;
    }

    int sum = 0;

    // To avoid exceeding the time limit, go up to `sqrt(num)`.
    for (int i = 2; i <= sqrt(num); ++i) {
      if (num % i == 0) {

        // Adds up both the divisor and the result at the same time.
        sum += i + num / i;
      }
    }

    return sum + 1 == num;
  }
};
```
