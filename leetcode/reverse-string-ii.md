---
name: "Reverse String II"
title: "LeetCode Reverse String II Solution"
description: "Solution for given a string s and an integer k, reverse the first k characters for every 2k characters counting from the start of the string. If there are fewer than k characters left, reverse all of them. If there are less than 2k but greater than or equal to k characters, then reverse the first k characters and left the other as original."
published: "2021-07-30 PDT"
modified: "2021-08-29 PDT"
---

# Reverse String II Problem & Solution

Given a string `s` and an integer `k`, reverse the first `k` characters for every `2k` characters counting from the start of the string.

If there are fewer than `k` characters left, reverse all of them.
If there are less than `2k` but greater than or equal to `k` characters, then reverse the first `k` characters and left the other as original.

See the [reverse string ii problem on LeetCode](https://leetcode.com/problems/reverse-string-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string reverseStr(string s, int k) {
    for (int i = 0; i < s.size(); i += 2 * k) {
      reverse(s.begin() + i, min(s.end(), s.begin() + i + k));
    }

    return s;
  }
};
```
