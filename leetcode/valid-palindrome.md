---
name: "Valid Palindrome"
title: "LeetCode Valid Palindrome Solution"
description: "Solution for the valid palindrome problem from LeetCode."
published: "2021-06-09 PDT"
modified: "2021-06-09 PDT"
---

# Valid Palindrome Problem & Solution

Given a string `s`, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

See the [valid palindrome problem on LeetCode](https://leetcode.com/problems/valid-palindrome).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPalindrome(string s) {
    int i = 0;
    int j = s.size() - 1;
    while (i < j) {
      while (i < j && !isalnum(s[i])) {
        ++i;
      }

      while (j > i && !isalnum(s[j])) {
        --j;
      }

      if (i < j && tolower(s[i]) != tolower(s[j])) {
        return false;
      }

      ++i;
      --j;
    }

    return true;
  }
};
```
