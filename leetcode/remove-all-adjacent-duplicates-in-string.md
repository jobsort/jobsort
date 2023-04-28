---
name: "Remove All Adjacent Duplicates in String"
title: "LeetCode Remove All Adjacent Duplicates in String Solution"
description: "Solution for the remove all adjacent duplicates in string problem from LeetCode."
published: "2022-12-12 PDT"
modified: "2022-12-12 PDT"
---

# Remove All Adjacent Duplicates in String Problem & Solution

See the [remove all adjacent duplicates in string problem on LeetCode](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string removeDuplicates(string s) {
    stack<char> ss;
    for (char c : s) {
      if (!ss.empty() && ss.top() == c) {
        ss.pop();
      } else {
        ss.push(c);
      }
    }

    string result;
    while (!ss.empty()) {
      result += ss.top();
      ss.pop();
    }

    reverse(result.begin(), result.end());
    return result;
  }
};
```
