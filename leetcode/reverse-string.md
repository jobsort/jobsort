---
name: "Reverse String"
title: "LeetCode Reverse String Solution"
description: "Solution for the reverse string problem from LeetCode."
published: "2021-07-08 PDT"
modified: "2021-07-08 PDT"
---

# Reverse String Problem & Solution

Write a function that reverses a string.
The input string is given as an array of characters `s`.

See the [reverse string problem on LeetCode](https://leetcode.com/problems/reverse-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  void reverseString(vector<char>& s) {
    reverse(s.begin(), s.end());
  }
};
```
