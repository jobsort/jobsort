---
name: "Word Pattern"
title: "LeetCode Word Pattern Solution"
description: "Solution for the word pattern problem from LeetCode."
published: "2021-07-19 PDT"
modified: "2021-07-19 PDT"
---

# Word Pattern Problem & Solution

Given a `pattern` and a string `s`, find if `s` follows the same `pattern`.
Here follow means a full match, such that there is a bijection between a letter in `pattern` and a non-empty word in `s`.

See the [word pattern problem on LeetCode](https://leetcode.com/problems/word-pattern).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool wordPattern(string pattern, string s) {
    int spaces = 0;
    for (int i = 0; i < s.size(); ++i) {
      if (s[i] == ' ') {
        ++spaces;
      }
    }

    if (pattern.size() != spaces + 1) {
      return false;
    }

    unordered_map<string, char> map;
    vector<bool> used(26, false);

    size_t last = 0;
    size_t next = 0;
    int i = 0;

    while ((next = s.find(" ", last)) != string::npos) {
      string token = s.substr(last, next - last);

      if (map.find(token) == map.end()) {
        if (!used[pattern[i] - 'a']) {
          map[token] = pattern[i];
          used[pattern[i] - 'a'] = true;
        } else {
          return false;
        }
      } else if (map[token] != pattern[i]) {
        return false;
      }

      last = next + 1;
      ++i;
    }

    string token = s.substr(last);
    if (map.find(token) == map.end()) {
      return used[pattern[i] - 'a'] == false;
    } else if (map[token] != pattern[i]) {
      return false;
    }

    return true;
  }
};
```
