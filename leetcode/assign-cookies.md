---
name: "Assign Cookies"
title: "LeetCode Assign Cookies Solution"
description: "Solution for the assign cookies problem from LeetCode."
published: "2021-07-28 PDT"
modified: "2021-07-28 PDT"
---

# Assign Cookies Problem & Solution

Assume you are an awesome parent and want to give your children some cookies.
But, you should give each child at most one cookie.

Each child `i` has a greed factor `g[i]`, which is the minimum size of a cookie that the child will be content with; and each cookie `j` has a size `s[j]`.
If `s[j] >= g[i]`, we can assign the cookie `j` to the child `i`, and the child `i` will be content.
Your goal is to maximize the number of your content children and output the maximum number.

See the [assign cookies problem on LeetCode](https://leetcode.com/problems/assign-cookies).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findContentChildren(vector<int>& g, vector<int>& s) {
    sort(g.begin(), g.end());
    sort(s.begin(), s.end());

    int i = 0;
    int j = 0;
    while (i < g.size()) {
      while (j < s.size() && s[j] < g[i]) {
        ++j;
      }

      if (j == s.size()) {
        break;
      }

      ++i;
      ++j;
    }

    return i;
  }
};
```
