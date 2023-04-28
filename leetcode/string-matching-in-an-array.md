---
name: "String Matching in an Array"
title: "LeetCode String Matching in an Array Solution"
description: "Solution for given an array of string words. Return all strings in words which is substring of another word in any order.  String words[i] is substring of words[j], if can be obtained removing some characters to left and/or right side of words[j]."
published: "2021-08-31 PDT"
modified: "2021-08-31 PDT"
---

# String Matching in an Array Problem & Solution

Given an array of string `words`.
Return all strings in `words` which is substring of another word in any order.

String `words[i]` is substring of `words[j]`, if can be obtained removing some characters to left and/or right side of `words[j]`.

See the [string matching in an array problem on LeetCode](https://leetcode.com/problems/string-matching-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> stringMatching(vector<string>& words) {
    set<string> result;

    for (int i = 0; i < words.size(); ++i) {
      for (int j = 0; j < words.size(); ++j) {
        if (i != j && words[i].find(words[j]) != string::npos) {
          result.insert(words[j]);
        }
      }
    }

    return vector<string>(result.begin(), result.end());
  }
};
```
