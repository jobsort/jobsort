---
name: "Shortest Distance to a Character"
title: "LeetCode Shortest Distance to a Character Solution"
description: "Solution for given a string s and a character c that occurs in s, return an array of integers answer where answer.length == s.length and answer[i] is the distance from index i to the closest occurrence of character c in s. The distance between two indices i and j is abs(i - j), where abs is the absolute value function."
published: "2021-12-20 PDT"
modified: "2021-12-20 PDT"
---

# Shortest Distance to a Character Problem & Solution

Given a string `s` and a character `c` that occurs in `s`, return an array of integers `answer` where `answer.length == s.length` and `answer[i]` is the distance from index `i` to the closest occurrence of character `c` in `s`.

The distance between two indices `i` and `j` is `abs(i - j)`, where `abs` is the absolute value function.

See the [shortest distance to a character problem on LeetCode](https://leetcode.com/problems/shortest-distance-to-a-character).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> shortestToChar(string s, char c) {
    vector<int> dist(s.size(), 1e4);

    for (int i = 0; i < s.size(); ++i) {
      if (s[i] == c) {
        dist[i] = 0;
      }
    }

    for (int i = 1; i < s.size(); ++i) {
      dist[i] = min(dist[i], dist[i - 1] + 1);
    }

    for (int i = s.size() - 2; i >= 0; --i) {
      dist[i] = min(dist[i], dist[i + 1] + 1);
    }

    return dist;
  }
};
```
