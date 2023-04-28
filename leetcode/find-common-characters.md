---
name: "Find Common Characters"
title: "LeetCode Find Common Characters Solution"
description: "Solution for given a string array words, return an array of all characters that show up in all strings within the words (including duplicates). You may return the answer in any order."
published: "2021-12-14 PDT"
modified: "2021-12-14 PDT"
---

# Find Common Characters Problem & Solution

Given a string array `words`, return an array of all characters that show up in all strings within the `words` (including duplicates).
You may return the answer in any order.

See the [find common characters problem on LeetCode](https://leetcode.com/problems/find-common-characters).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> commonChars(vector<string>& words) {
    vector<int> freq('z' - 'a' + 1, numeric_limits<int>::max());
    for (int i = 0; i < words.size(); ++i) {
      vector<int> row('z' - 'a' + 1, 0);
      for (int j = 0; j < words[i].size(); ++j) {
        ++row[words[i][j] - 'a'];
      }

      for (int j = 0; j < row.size(); ++j) {
        freq[j] = min(freq[j], row[j]);
      }
    }

    vector<string> result;
    for (int i = 0; i < freq.size(); ++i) {
      for (int j = 0; j < freq[i]; ++j) {
        result.push_back(string(1, i + 'a'));
      }
    }

    return result;
  }
};
```
