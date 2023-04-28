---
name: "Longest Substring without Repeating Characters"
title: "LeetCode Longest Substring without Repeating Characters Solution"
description: "Solution for the longest substring without repeating characters problem from LeetCode."
published: "2022-03-31 PDT"
modified: "2022-03-31 PDT"
---

# Longest Substring without Repeating Characters Problem & Solution

See the [longest substring without repeating characters problem on LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int lengthOfLongestSubstring(string s) {
    int best = 0;
    int i = 0;
    int freq[256] = {};
    for (int j = 0; j < s.size(); ++j) {
      ++freq[s[j]];

      char dup;
      int k;
      for (k = 0; k < 256; ++k) {
        if (freq[k] > 1) {
          dup = (char)k;
          break;
        }
      }

      if (k == 256) {
        best = max(best, j - i + 1);
      } else {
        while (i < j && s[i] != dup) {
          —freq[s[i]];
          ++i;
        }

        —freq[s[i]];
        ++i;
      }
    }

    return best;
  }
};
```
