---
name: "Minimum Window Substring"
title: "LeetCode Minimum Window Substring Solution"
description: "Solution for the minimum window substring problem from LeetCode."
published: "2023-01-25 PDT"
modified: "2023-01-25 PDT"
---

# Minimum Window Substring Problem & Solution

See the [minimum window substring problem on LeetCode](https://leetcode.com/problems/minimum-window-substring).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string minWindow(string s, string t) {
    unordered_map<char, int> tmap;
    for (char c : t) {
      ++tmap[c];
    }

    string result = "";
    int best = numeric_limits<int>::max();

    unordered_map<char, int> smap;
    int i = 0, j = 0;
    while (j < s.size()) {
      while (j < s.size()) {
        ++smap[s[j++]];

        bool ok = true;
        for (auto [k, v] : tmap) {
          if (smap[k] < v) {
            ok = false;
            break;
          }
        }

        if (ok) {
          break;
        }
      }

      while (i < j) {
        auto found = tmap.find(s[i]);
        if (found == tmap.end()) {
          ++i;
          continue;
        }

        if (smap[s[i]] > tmap[s[i]]) {
          --smap[s[i++]];
        } else {
          break;
        }
      }

      bool ok = true;
      for (auto [k, v] : tmap) {
        if (smap[k] < v) {
          ok = false;
          break;
        }
      }

      if (ok && best > j - i) {
        best = j - i;
        result = s.substr(i, best);
      }
    }

    return result;
  }
};
```
