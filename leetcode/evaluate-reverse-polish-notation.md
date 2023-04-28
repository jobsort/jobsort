---
name: "Evaluate Reverse Polish Notation"
title: "LeetCode Evaluate Reverse Polish Notation Solution"
description: "Solution for the evaluate reverse Polish notation problem from LeetCode."
published: "2023-03-04 PDT"
modified: "2023-03-04 PDT"
---

# Evaluate Reverse Polish Notation Problem & Solution

See the [evaluate reverse Polish notation problem on LeetCode](https://leetcode.com/problems/evaluate-reverse-polish-notation).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int evalRPN(vector<string>& tokens) {
    stack<int> s;

    for (auto token : tokens) {
      if (token == "+" || token == "-" || token == "*" || token == "/") {
        int a = s.top(); s.pop();
        int b = s.top(); s.pop();

        if (token == "+") {
          s.push(a + b);
        } else if (token == "-") {
          s.push(b - a);
        } else if (token == "*") {
          s.push(a * b);
        } else if (token == "/") {
          s.push(b / a);
        }
      } else {
        s.push(stoi(token));
      }
    }

    return s.top();
  }
};
```
