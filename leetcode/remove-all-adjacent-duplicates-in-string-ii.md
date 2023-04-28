---
name: "Remove All Adjacent Duplicates in String II"
title: "LeetCode Remove All Adjacent Duplicates in String II Solution"
description: "Solution for the remove all adjacent duplicates in string ii problem from LeetCode."
published: "2022-12-12 PDT"
modified: "2022-12-12 PDT"
---

# Remove All Adjacent Duplicates in String II Problem & Solution

See the [remove all adjacent duplicates in string ii problem on LeetCode](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string removeDuplicates(string s, int k) {
    stack<tuple<char, int>> ss;

    for (char c : s) {
      if (!ss.empty() && get<0>(ss.top()) == c) {
        auto top = ss.top();
        get<1>(top) = get<1>(top) + 1;

        ss.pop();

        if (get<1>(top) != k) {
          ss.push(top);
        }
      } else {
        ss.push({c, 1});
      }
    }

    string result;
    while (!ss.empty()) {
      for (int i = 0; i < get<1>(ss.top()); ++i) {
        result += get<0>(ss.top());
      }
      ss.pop();
    }

    reverse(begin(result), end(result));
    return result;
  }
};
```
