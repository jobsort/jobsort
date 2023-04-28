---
name: "Increasing Decreasing String"
title: "LeetCode Increasing Decreasing String Solution"
description: "Solution for the increasing decreasing string problem from LeetCode."
published: "2022-04-07 PDT"
modified: "2022-04-07 PDT"
---

# Increasing Decreasing String Problem & Solution

See the [increasing decreasing string problem on LeetCode](https://leetcode.com/problems/increasing-decreasing-string).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string sortString(string s) {
    string t;
    int freq['z' - 'a' + 1] = {};
    for (char c : s) {
      ++freq[c - 'a'];
    }

    while (t.size() < s.size()) {
      for (char c = 'a'; c <= 'z'; ++c) {
        if (freq[c - 'a']-- > 0) {
          t += c;
        }
      }

      for (char c = 'z'; c >= 'a'; --c) {
        if (freq[c - 'a']-- > 0) {
          t += c;
        }
      }
    }

    return t;
  }
};
```
