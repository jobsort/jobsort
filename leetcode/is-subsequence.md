---
name: "Is Subsequence"
title: "LeetCode Is Subsequence Solution"
description: "Solution for the is subsequence problem from LeetCode."
published: "2021-07-24 PDT"
modified: "2021-07-24 PDT"
---

# Is Subsequence Problem & Solution

Given two strings `s` and `t`, return true if `s` is a subsequence of `t`, or false otherwise.

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

See the [is subsequence problem on LeetCode](https://leetcode.com/problems/is-subsequence).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isSubsequence(string s, string t) {
    int j = 0;
    for (int i = 0; i < s.size(); ++i) {
      while (j < t.size() && s[i] != t[j]) {
        ++j;
      }

      if (j == t.size()) {
        return false;
      }

      ++j;
    }

    return true;
  }
};
```
