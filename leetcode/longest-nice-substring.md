---
name: "Longest Nice Substring"
title: "LeetCode Longest Nice Substring Solution"
description: "Solution for the longest nice substring problem from LeetCode."
published: "2023-01-10 PDT"
modified: "2023-01-10 PDT"
---

# Longest Nice Substring Problem & Solution

See the [longest nice substring problem on LeetCode](https://leetcode.com/problems/longest-nice-substring).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string longestNiceSubstring(string s) {
    for (int i = s.size(); i >= 2; --i) {
      vector<int> freq1('z' - 'a' + 1),
                  freq2('Z' - 'A' + 1);
      for (int j = 0; j < s.size(); ++j) {
        if (s[j] >= 'a' && s[j] <= 'z') {
          ++freq1[s[j] - 'a'];
        } else {
          ++freq2[s[j] - 'A'];
        }

        if (j >= i) {
          if (s[j - i] >= 'a' && s[j - i] <= 'z') {
            --freq1[s[j - i] - 'a'];
          } else {
            --freq2[s[j - i] - 'A'];
          }
        }

        if (j >= i - 1) {
          int k;
          for (k = 0; k < freq1.size(); ++k) {
            if ((freq1[k] > 0 && freq2[k] == 0) ||
                (freq2[k] > 0 && freq1[k] == 0)) {
              break;
            }
          }

          if (k == freq1.size()) {
            return s.substr(j - i + 1, i);
          }
        }
      }
    }

    return "";
  }
};
```
