---
name: "DI String Match"
title: "LeetCode DI String Match Solution"
description: "Solution for a permutation perm of n + 1 integers of all the integers in the range [0, n] can be represented as a string s of length n where: s[i] == 'I' if perm[i] < perm[i + 1], and s[i] == 'D' if perm[i] > perm[i + 1]. Given a string s, reconstruct the permutation perm and return it. If there are multiple valid permutations perm, return any of them."
published: "2021-09-09 PDT"
modified: "2021-09-09 PDT"
---

# DI String Match Problem & Solution

A permutation `perm` of `n + 1` integers of all the integers in the range `[0, n]` can be represented as a string `s` of length `n` where:

- `s[i] == 'I'` if `perm[i] < perm[i + 1]`, and
- `s[i] == 'D'` if `perm[i] > perm[i + 1]`.

Given a string `s`, reconstruct the permutation `perm` and return it.
If there are multiple valid permutations `perm`, return any of them.

See the [DI string match problem on LeetCode](https://leetcode.com/problems/di-string-match).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> diStringMatch(string s) {
    int low = 0;
    int high = s.size();

    vector<int> result(s.size() + 1, 0);
    for (int i = 0; i < s.size(); ++i) {
      if (s[i] == 'I') {
        result[i] = low++;
      } else {
        result[i] = high--;
      }
    }

    result[s.size()] = low;

    return result;
  }
};
```
