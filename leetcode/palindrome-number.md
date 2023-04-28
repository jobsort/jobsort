---
name: "Palindrome Number"
title: "LeetCode Palindrome Number Solution"
description: "Solution for the palindrome number problem from LeetCode."
published: "2021-05-20 PDT"
modified: "2021-06-09 PDT"
---

# Palindrome Number Problem & Solution

Given an integer `x`, return true if `x` is palindrome integer. An integer is a palindrome when it reads the same backward as forward. For example, 121 is palindrome while 123 is not.

See the [palindrome number problem on LeetCode](https://leetcode.com/problems/palindrome-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPalindrome(int x) {
    if (x < 0) {
      return false;
    }

    // When reversing a signed int, its reverse can overflow, thus using unsigned int.
    uint y = 0;
    int tmp = x;
    while (tmp != 0) {
      y = y * 10 + tmp % 10;
      tmp /= 10;
    }

    while (x != 0) {
      if (x % 10 != y % 10) {
        return false;
      }

      x /= 10;
      y /= 10;
    }

    return true;
  }
};
```
